# Google Calendar Connector — คู่มือตั้งค่าและใช้งาน

## Google Calendar MCP ทำอะไรได้?

| ความสามารถ | ตัวอย่าง |
|-----------|---------|
| อ่านตาราง Events | "วันนี้มีประชุมอะไรบ้าง?" |
| สรุป Upcoming Events | "สัปดาห์หน้ามีกำหนดการอะไร?" |
| ค้นหา Events | "หาประชุม Budget Review ที่นัดไว้" |
| รายละเอียด Event | "ประชุม 14:00 มีใครเข้าร่วมบ้าง?" |
| รวมกับ Gmail | "ดูอีเมลที่เกี่ยวกับประชุมพรุ่งนี้" |

---

## การตั้งค่า Google Calendar Connector

### วิธีที่ 1: ผ่าน Claude Cowork Connectors Panel
1. เปิด Claude Desktop App
2. คลิก **Connectors** (ไอคอนด้านซ้าย)
3. หา **Google Calendar** → คลิก Connect
4. Sign In ด้วย Google Account
5. อนุญาต Permission ที่ขอ (Read-only Calendar)
6. ✅ พร้อมใช้งาน

### Permissions ที่ต้องการ
- `calendar.readonly` — อ่านข้อมูล Events (ไม่ต้องแก้ไข)
- ไม่ต้องการ Write Permission สำหรับการใช้งานพื้นฐาน

---

## Prompt สำหรับ Google Calendar

### Daily Schedule
```
"บอกฉันว่าวันนี้มีกำหนดการอะไรบ้างใน Google Calendar
แสดงเวลา ชื่อ Event และผู้เข้าร่วม (ถ้ามี)
เรียงตามเวลา"
```

### Weekly Overview
```
"สรุปกำหนดการสัปดาห์นี้ (จันทร์-ศุกร์):
- วันที่มีประชุมมากสุด
- Events ที่ต้องเตรียมตัวพิเศษ
- ช่วงว่างที่สามารถนัดเพิ่มได้"
```

### Meeting Preparation
```
"ประชุม [ชื่อ Event] เวลา [เวลา] วันนี้
ช่วยเตรียมฉันโดย:
1. สรุปว่าประชุมเรื่องอะไร (จากชื่อและคำอธิบาย)
2. ดู Email ที่เกี่ยวข้องใน Gmail
3. หาไฟล์ที่เกี่ยวข้องใน Google Drive
4. สร้าง Agenda สั้นๆ ให้ฉัน"
```

---

## Morning Briefing รวม Calendar + Gmail + Drive

```
"สร้าง Morning Briefing สำหรับวันนี้:

📅 CALENDAR:
- ประชุมทั้งหมดวันนี้ (เวลา + ชื่อ)
- Meeting ที่ต้องเตรียมพิเศษ

📧 GMAIL:
- Email เร่งด่วนที่ต้องตอบภายในวันนี้
- Email ที่ต้องการ Action

📁 DRIVE:
- ไฟล์ที่แก้ไขล่าสุด (เมื่อวาน)
- ไฟล์ที่แชร์กับฉันใหม่

⚡ TOP 3 สิ่งที่ต้องทำวันนี้"
```
