# Morning Briefing Workflow — คู่มือออกแบบ

## เป้าหมาย
สร้าง Automated Morning Briefing ที่รวมข้อมูลจากทุก Connector
ใช้เวลา < 2 นาทีในการอ่าน ทำให้เริ่มต้นวันทำงานได้ทันที

---

## Template: Morning Briefing Prompt

```
ทุกเช้าเวลา 8:00 น. สร้าง Morning Briefing ดังนี้:

# 🌅 Morning Briefing — [วันที่วันนี้]

## 📅 กำหนดการวันนี้
[ดูจาก Google Calendar]
- [เวลา] [ชื่อ Meeting] — [ผู้เข้าร่วม]
- ...

## 📧 Email ที่ต้องตอบด่วน
[ดูจาก Gmail — Email ที่ได้รับ 24 ชั่วโมงที่ผ่านมา]
- จาก: [ผู้ส่ง] | เรื่อง: [หัวข้อ] | ต้องการ: [Action]
- ...

## 📁 ไฟล์ที่อัปเดตล่าสุด
[ดูจาก Google Drive]
- [ชื่อไฟล์] — แก้ไขโดย [คน] เมื่อ [เวลา]

## ⚡ Top 5 สิ่งที่ต้องทำวันนี้
1.
2.
3.
4.
5.

## 💡 Reminder
- งานที่ค้างจากเมื่อวาน (ถ้ามี)
- Deadline ภายในสัปดาห์นี้
```

---

## Scheduled Task Setup

ตั้ง Automated Briefing ใน Claude Cowork:

```
ชื่อ Task: "Daily Morning Briefing"
Schedule: ทุกวันจันทร์-ศุกร์ เวลา 08:00 น.
Action: รัน Morning Briefing Prompt
Output: บันทึกใน Google Drive/Briefings/[วันที่].md
Notification: ส่ง Summary ไป Slack #personal-briefings
```

---

## ตัวอย่าง Output จริง

```
# 🌅 Morning Briefing — วันอังคารที่ 15 กรกฎาคม 2568

## 📅 กำหนดการวันนี้
- 09:30 Standup กับทีม Product (Google Meet) — 5 คน
- 14:00 Budget Review กับ CFO — 3 คน
- 16:00 1:1 กับ Direct Report

## 📧 Email ที่ต้องตอบด่วน
- จาก: สมชาย@บริษัท.com | เรื่อง: ขอ Approve งบ Q3 | ต้องการ: อนุมัติ
- จาก: client@abc.com | เรื่อง: Follow up proposal | ต้องการ: ตอบภายในวันนี้

## ⚡ Top 5 สิ่งที่ต้องทำวันนี้
1. เตรียม Budget Review Presentation (ก่อน 14:00)
2. ตอบ Email ลูกค้า ABC
3. Approve งบ Q3 ของสมชาย
4. ส่ง Weekly Report ให้ทีม
5. Review Draft Contract จาก Legal
```

---

## Customization สำหรับแต่ละบทบาท

**สำหรับ Manager:** เพิ่ม Team Updates จาก Slack
**สำหรับ CFO:** เพิ่ม Daily Financial Summary จาก Google Drive
**สำหรับ Sales:** เพิ่ม Pipeline Updates จาก CRM
**สำหรับ Developer:** เพิ่ม GitHub PR Reviews ที่รอ
