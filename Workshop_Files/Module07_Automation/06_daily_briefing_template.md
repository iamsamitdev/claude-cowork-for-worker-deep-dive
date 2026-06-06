# Template: Daily Morning Briefing

## Prompt สำหรับสร้าง Scheduled Task

```
ชื่อ Task: Daily Morning Briefing
Trigger: ทุกวัน เวลา 8:00 น. (จันทร์-ศุกร์)

งาน:
1. อ่าน Email ใหม่ตั้งแต่เมื่อคืน (ถ้าเชื่อมต่อ Gmail)
2. อ่าน Slack Messages จาก Channels สำคัญ (ถ้าเชื่อมต่อ)
3. อ่านไฟล์ tasks_today.md (ถ้ามี)
4. อ่าน calendar_today.txt (ถ้ามี)

สร้างไฟล์: briefing_YYYY-MM-DD.md
โครงสร้าง:
## 🌅 Good Morning! — วันที่ [วัน/เดือน/ปี]

### 📧 Email ที่ต้องตอบ
[รายการ email ด่วน]

### 💬 Slack สำคัญ
[highlights จาก Slack]

### 📋 Task วันนี้
[tasks จาก tasks_today.md]

### 🗓️ ประชุมวันนี้
[ประชุมจาก calendar]

### ⚡ Priority Action
[Top 3 สิ่งที่ต้องทำก่อน]
```
