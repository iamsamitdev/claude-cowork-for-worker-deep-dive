# AI Chatbot vs Agentic AI — เปรียบเทียบเชิงลึก

## ความแตกต่างหลัก

| มิติ | AI Chatbot | Agentic AI |
|------|-----------|------------|
| การตอบสนอง | Reactive (ตอบเมื่อถูกถาม) | Proactive (วางแผนและดำเนินงาน) |
| จำนวน Step | Single-turn | Multi-step |
| การใช้ Tools | ไม่มี | มี (ไฟล์, API, เว็บ) |
| ความจำ | ลืมเมื่อปิด Session | จำ Context ได้ต่อเนื่อง |
| Output | ข้อความเท่านั้น | ไฟล์, actions, รายงาน |
| ตัวอย่างงาน | "สรุปย่อหน้านี้" | "สรุปไฟล์ทั้งโฟลเดอร์แล้วสร้าง Excel" |

## Agent Loop ของ Claude

```
USER REQUEST
    ↓
[THINK] — วิเคราะห์งาน, วางแผน steps
    ↓
[ACT] — ใช้ Tool (อ่านไฟล์, รันโค้ด, เรียก API)
    ↓
[OBSERVE] — ดูผลลัพธ์จาก Tool
    ↓
[THINK AGAIN] — ประเมินผล, ปรับแผน
    ↓
[ACT AGAIN] — ดำเนินการต่อ
    ↓
FINAL OUTPUT → ส่งผลกลับให้ User
```

## ตัวอย่าง Use Case เปรียบเทียบ

### Chatbot Style
User: "ช่วยเขียนรายงานประชุมให้หน่อย"
AI: "กรุณาวางเนื้อหาการประชุมมาให้ฉันสรุป"
→ User ต้องทำทุกอย่างเอง

### Agentic Style
User: "สรุปบันทึกการประชุมทั้งหมดในเดือนนี้"
AI:
1. อ่านไฟล์ทั้งหมดในโฟลเดอร์ meetings/
2. วิเคราะห์และสรุปแต่ละการประชุม
3. รวม Action Items ทั้งหมด
4. สร้างไฟล์ monthly_meeting_summary.docx
→ Claude ทำงานทั้งหมดโดยอัตโนมัติ
