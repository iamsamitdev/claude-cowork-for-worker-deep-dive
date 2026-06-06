# Claude Cowork vs Claude Code — ตารางเปรียบเทียบฉบับสมบูรณ์

## ภาพรวม

Claude มีสองรูปแบบหลักสำหรับ Agentic AI:

| ประเด็น | Claude Cowork | Claude Code |
|---------|--------------|-------------|
| **ผู้ใช้งานหลัก** | Knowledge Worker, Office User, ไม่ต้องมีพื้นฐาน Code | Developer, Engineer, Technical User |
| **Interface** | Desktop App (GUI — ใช้ง่าย) | Terminal / CLI (Command Line) |
| **ติดตั้งผ่าน** | Claude Desktop App → เปิด Cowork Mode | `npm install -g @anthropic-ai/claude-code` |
| **Operating System** | macOS, Windows | macOS, Linux, Windows (WSL) |
| **ราคา** | Claude Pro/Max Subscription | Claude Pro/Max + usage |
| **Use Case หลัก** | เอกสาร, Email, Connectors, Automation | เขียนโค้ด, Debug, Refactor, DevOps |
| **MCP Support** | ✓ (GUI-based Config) | ✓ (JSON Config ใน Terminal) |
| **Skills/Plugins** | ✓ (ติดตั้งผ่าน Desktop App) | ✓ (ผ่าน config file) |
| **Scheduled Tasks** | ✓ (GUI) | ❌ (ต้อง implement เอง) |
| **File Access** | ✓ (เลือก Folder ผ่าน GUI) | ✓ (ทั้ง Filesystem) |
| **Shell Access** | จำกัด (sandbox) | ✓ (เต็มรูปแบบ) |
| **Git Integration** | ❌ | ✓ (เต็มรูปแบบ) |

---

## เมื่อไหร่ควรใช้อะไร?

### ใช้ Claude Cowork เมื่อ:
- ต้องการสร้างหรือแก้ไขเอกสาร Office (Excel, Word, PPT)
- ต้องการเชื่อมต่อกับ Gmail, Google Drive, Slack
- ต้องการตั้ง Scheduled Task แบบ No-Code
- ไม่มีพื้นฐาน Programming
- ทำงานด้านบัญชี, การเงิน, HR, การตลาด

### ใช้ Claude Code เมื่อ:
- ต้องการเขียนหรือแก้ Code (Python, JS, TypeScript, ฯลฯ)
- ต้องการ Debug หรือ Refactor โค้ด
- ต้องการ Deploy หรือ Run Script
- ทำงานด้าน Development, DevOps, Data Engineering
- ต้องการ Full Shell Access

---

## Decision Framework: "ฉันควรใช้อะไร?"

```
ฉันต้องการทำอะไร?
│
├── เขียน / แก้ Code หรือ Script
│   └── → ใช้ Claude Code
│
├── จัดการเอกสาร / สรุปข้อมูล / สร้างรายงาน
│   └── → ใช้ Claude Cowork
│
├── เชื่อมต่อ Gmail / Drive / Slack / Calendar
│   └── → ใช้ Claude Cowork
│
├── ตั้ง Automation Task แบบ No-Code
│   └── → ใช้ Claude Cowork
│
└── ทั้งสองอย่าง (พัฒนาแอปพร้อมสร้างเอกสาร)
    └── → ใช้ทั้งคู่ตามบทบาท
```

---

## ตัวอย่างการใช้งานจริง

### Scenario 1: CFO ต้องการ Financial Report รายเดือน
- **ใช้:** Claude Cowork
- **เหตุผล:** อ่านงบการเงิน CSV, สร้าง Word Report, ส่ง Email อัตโนมัติ
- **ไม่ต้องเขียน Code เลย**

### Scenario 2: Developer ต้องการ Refactor API
- **ใช้:** Claude Code
- **เหตุผล:** ต้องการอ่าน/แก้ Code, Run Tests, Git Commit
- **ทำงานใน Terminal โดยตรง**

### Scenario 3: Marketing Manager สร้าง Campaign Report
- **ใช้:** Claude Cowork
- **เหตุผล:** ดึงข้อมูลจาก Drive, วิเคราะห์ข้อมูล, สร้าง PPT
- **ไม่ต้องมีพื้นฐาน Programming**

### Scenario 4: Data Engineer Build ETL Pipeline
- **ใช้:** Claude Code
- **เหตุผล:** เขียน Python Script, Run SQL, Deploy Pipeline
- **ต้องการ Full Shell Access**

---

## แบบฝึกหัด

**โจทย์:** จับคู่แต่ละ Use Case กับ Tool ที่เหมาะสม

| Use Case | Cowork | Code |
|----------|--------|------|
| สรุป Email 50 ฉบับในสัปดาห์นี้ | | |
| เขียน REST API ด้วย Node.js | | |
| สร้าง Excel Budget Tracker | | |
| Deploy Docker Container | | |
| ตั้ง Daily Report อัตโนมัติ | | |
| Debug ข้อผิดพลาดใน Python Script | | |
| วิเคราะห์งบการเงินรายไตรมาส | | |
| Push Code ขึ้น GitHub | | |

**เฉลย:** Cowork: 1, 3, 5, 7 | Code: 2, 4, 6, 8
