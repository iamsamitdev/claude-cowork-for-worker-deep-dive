# MCP Architecture Overview
## Model Context Protocol — สถาปัตยกรรมและหลักการทำงาน

---

## 1. MCP คืออะไร?

**Model Context Protocol (MCP)** คือมาตรฐานเปิด (Open Protocol) ที่พัฒนาโดย Anthropic เพื่อเป็น "สะพาน" เชื่อมต่อระหว่าง AI (Claude) กับบริการและข้อมูลภายนอก โดยไม่ต้องเขียนโค้ดเชื่อมต่อเอง

### เปรียบเทียบง่ายๆ

| แบบเดิม (ไม่มี MCP) | แบบใหม่ (มี MCP) |
|---|---|
| Claude รู้เฉพาะข้อมูลที่คุณพิมพ์ใน Chat | Claude เข้าถึงข้อมูลจริงจาก Gmail, Drive, Calendar ได้โดยตรง |
| ต้อง Copy & Paste ข้อมูลเข้ามาเอง | Claude ดึงข้อมูลให้อัตโนมัติตามที่คุณสั่ง |
| ทำงานได้แค่ในกล่อง Chat | ทำงานข้ามระบบได้ใน Prompt เดียว |

---

## 2. สถาปัตยกรรม MCP (Architecture Diagram)

```
┌─────────────────────────────────────────────────────────────┐
│                    คำสั่งของคุณ (Prompt)                      │
│    "สรุปอีเมลวันนี้ + เพิ่ม Task ใน Calendar + แจ้ง Slack"    │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│                    Claude (AI Brain)                         │
│         วิเคราะห์ → วางแผน → สั่งการ → สังเคราะห์            │
└────────┬───────────────┬───────────────┬────────────────────┘
         │               │               │
         ▼               ▼               ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│  MCP Server  │ │  MCP Server  │ │  MCP Server  │
│   (Gmail)    │ │  (Calendar)  │ │   (Slack)    │
│  ทำงานใน     │ │  ทำงานใน     │ │  ทำงานใน     │
│  เครื่องคุณ  │ │  เครื่องคุณ  │ │  เครื่องคุณ  │
└──────┬───────┘ └──────┬───────┘ └──────┬───────┘
       │                │                │
       ▼                ▼                ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│  Gmail API   │ │ Google Cal.  │ │  Slack API   │
│  (Cloud)     │ │  API (Cloud) │ │  (Cloud)     │
└──────┬───────┘ └──────┬───────┘ └──────┬───────┘
       │                │                │
       ▼                ▼                ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│   อีเมลจริง  │ │ นัดหมายจริง  │ │ ข้อความจริง  │
│  ของคุณ      │ │  ของคุณ      │ │  ของคุณ      │
└──────────────┘ └──────────────┘ └──────────────┘
```

### อธิบาย Flow ทีละขั้น

1. **คุณพิมพ์ Prompt** — บอก Claude ว่าต้องการอะไร (เป็นภาษาธรรมดา)
2. **Claude วิเคราะห์** — ระบุว่าต้องใช้บริการใดบ้าง และต้องทำอะไรก่อนหลัง
3. **Claude เรียก MCP Server** — ส่งคำสั่งไปยัง MCP Server ที่ติดตั้งในเครื่องคุณ
4. **MCP Server ติดต่อ API** — ใช้ Token (สิทธิ์) ที่คุณให้ไว้ เรียก API ของบริการนั้น
5. **ข้อมูลจริงไหลกลับ** — ผ่าน MCP Server → Claude → สังเคราะห์เป็นคำตอบ

> **สำคัญ:** MCP Server ทำงานใน **เครื่องของคุณ** ข้อมูลไม่ถูกส่งผ่านเซิร์ฟเวอร์กลาง ทำให้ปลอดภัยกว่าการส่ง API Key โดยตรง

---

## 3. Token และ Permission (สิทธิ์การเข้าถึง)

### OAuth 2.0 — ระบบอนุญาตสิทธิ์มาตรฐาน

```
คุณ ──[กด Authorize]──▶ Google/Slack/etc.
      ◀──[Token]──────── (ไม่ต้องใส่ Password)
Token ──[เก็บใน MCP Server]──▶ ใช้เรียก API ได้
```

**Token** เปรียบเหมือน "บัตรผ่าน" ที่มีสิทธิ์จำกัด — บริการที่ออกให้กำหนดได้ว่าอนุญาตทำอะไรได้บ้าง

### Scope ของ Connector แต่ละตัว

| Connector | Scope (สิทธิ์) | Claude ทำได้ | Claude ทำไม่ได้ |
|---|---|---|---|
| **Google Drive** | `drive.readonly` | อ่านไฟล์, ค้นหา, สรุปเนื้อหา | ลบไฟล์, แชร์ให้คนอื่น |
| **Gmail** | `gmail.readonly` | อ่านอีเมล, ค้นหา, สรุป | ส่งอีเมล (ถ้าไม่ grant `gmail.send`) |
| **Google Calendar** | `calendar` | อ่าน+สร้าง+แก้ไขนัด | ลบ Calendar ทั้งหมด |
| **Slack** | `channels:read` `chat:write` | อ่านข้อความ, ส่งข้อความ | ลบ Workspace, เพิ่มสมาชิก |

> **หลักการ Least Privilege:** ให้สิทธิ์เท่าที่จำเป็นเท่านั้น — หากใช้แค่อ่าน ก็ grant แค่ `readonly`

---

## 4. MCP vs วิธีเชื่อมต่อแบบเดิม

| ประเด็น | Traditional API | MCP |
|---|---|---|
| **ผู้ใช้งาน** | Developer (เขียน Code) | ทุกคน (ไม่ต้องโค้ด) |
| **การตั้งค่า** | เขียน Code + จัดการ Token เอง | กด Authorize ใน Cowork GUI |
| **ความยืดหยุ่น** | Fixed Function ตามที่โค้ดไว้ | Natural Language — สั่งอะไรก็ได้ |
| **ความปลอดภัย** | API Key เก็บใน Code (เสี่ยง) | Token เก็บใน Local MCP Server |
| **Multi-service** | ต้องเขียนโค้ด Integration | Claude จัดการ Orchestration เอง |
| **ตัวอย่าง** | เขียน Python เรียก Gmail API | พิมพ์ "สรุปอีเมลวันนี้" |

---

## 5. Connector ที่ใช้ใน Workshop นี้

### Google Drive Connector
```
สิ่งที่ Claude ทำได้:
✅ ค้นหาไฟล์ตามชื่อหรือเนื้อหา
✅ อ่านและสรุป Google Docs / PDF
✅ เปรียบเทียบเนื้อหาระหว่างไฟล์
✅ ดึงข้อมูลจาก Google Sheets

ตัวอย่าง Prompt:
"หาไฟล์ proposal ล่าสุดใน Drive แล้วสรุปประเด็นสำคัญ"
```

### Gmail Connector
```
สิ่งที่ Claude ทำได้:
✅ อ่านและสรุปอีเมล
✅ ค้นหาอีเมลตามเงื่อนไข (sender, subject, date)
✅ จัดหมวดหมู่อีเมลตาม Priority
✅ ร่างอีเมลตอบกลับ (คุณส่งเอง)

ตัวอย่าง Prompt:
"อีเมลไหนบ้างที่ยังไม่ได้ตอบและมาจากลูกค้า ช่วยสรุปให้หน่อย"
```

### Google Calendar Connector
```
สิ่งที่ Claude ทำได้:
✅ ดูตาราง meeting ของวัน/สัปดาห์
✅ สร้างนัดหมายใหม่
✅ หาช่วงเวลาว่างสำหรับประชุม
✅ สรุปว่ามีนัดอะไรบ้างและเตรียมอะไร

ตัวอย่าง Prompt:
"วันพรุ่งนี้มีประชุมอะไรบ้าง และแต่ละนัดต้องเตรียมอะไร"
```

### Slack Connector
```
สิ่งที่ Claude ทำได้:
✅ อ่านข้อความใน Channel ที่มีสิทธิ์
✅ ส่งข้อความหรือ Report ไปยัง Channel
✅ สรุปการสนทนาย้อนหลัง
✅ ค้นหาข้อมูลใน Thread เก่า

ตัวอย่าง Prompt:
"สรุปสิ่งที่คุยกันใน #project-alpha วันนี้และส่งไปที่ #daily-summary"
```

---

## 6. ข้อควรระวังด้านความปลอดภัย

### ✅ สิ่งที่ MCP ทำเพื่อความปลอดภัย
- Token เก็บใน Local เครื่องคุณ ไม่อัปโหลดขึ้น Cloud
- ใช้ OAuth มาตรฐาน — ไม่ต้องใช้ Password
- สิทธิ์จำกัดตาม Scope ที่กำหนด
- คุณเพิกถอนสิทธิ์ได้ทุกเมื่อจาก Google/Slack Account Settings

### ⚠️ สิ่งที่ควรระวัง
- ตรวจสอบ Scope ก่อน Authorize เสมอ
- ไม่ให้สิทธิ์ Delete/Admin ถ้าไม่จำเป็น
- ระวัง Prompt Injection — ถ้าเนื้อหาใน Drive มีคำสั่งแปลกๆ Claude อาจทำตาม
- Log ว่า Claude ทำอะไรบ้าง โดยเฉพาะ Action ที่ Write ข้อมูล

---

## 7. การตั้งค่า Connector ใน Claude Cowork (Quick Guide)

```
1. เปิด Claude Cowork Desktop App
2. ไปที่ Settings → Connectors
3. เลือก Connector ที่ต้องการ (เช่น Gmail)
4. กด "Connect" → Browser จะเปิดหน้า Google Login
5. เลือก Account และกด "Allow"
6. กลับมาที่ Cowork — สถานะจะเปลี่ยนเป็น "Connected ✅"
7. ทดสอบ: พิมพ์ "อีเมลล่าสุดของฉันคืออะไร"
```

---

## แหล่งอ้างอิง

- [MCP Official Specification](https://modelcontextprotocol.io) — Anthropic
- [Claude Cowork Connector Setup](https://docs.claude.ai) — Anthropic Docs
- [OAuth 2.0 Explained](https://oauth.net/2/) — oauth.net
- [Google API Scopes Reference](https://developers.google.com/identity/protocols/oauth2/scopes) — Google Developers
