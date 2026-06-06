# คู่มือ Scheduled Tasks ใน Claude Cowork

## Scheduled Tasks คืออะไร?
คุณสมบัติที่ให้ Claude ทำงานอัตโนมัติตามเวลาที่กำหนด
โดยไม่ต้องสั่งทุกครั้ง

## วิธีสร้าง Scheduled Task

### ผ่าน Claude (Natural Language)
"ตั้ง Scheduled Task: ทุกเช้าเวลา 8:00 น. วันจันทร์-ศุกร์
ให้สรุปไฟล์ใน Drive ที่แก้ไขล่าสุด 24 ชั่วโมง
แล้วบันทึกใน daily_briefing.md"

### ผ่าน Skill Tool (ถ้ามี)
1. เรียกใช้ Schedule Skill
2. ระบุ: Trigger (เวลา/เหตุการณ์), Task (งานที่ทำ), Output (ผลลัพธ์)

## ประเภท Trigger

| Trigger | ตัวอย่าง |
|---------|---------|
| Time-based | ทุกวันเวลา 8:00 น. |
| Day-of-week | ทุกวันศุกร์เวลา 17:00 น. |
| Monthly | ทุกวันที่ 1 เวลา 9:00 น. |
| On Demand | เรียกเมื่อต้องการ |

## Best Practices
✅ ตั้งชื่อ Task ชัดเจน
✅ ระบุ Output File ที่แน่นอน
✅ เพิ่ม Error Handling: "ถ้าไม่มีไฟล์ใหม่ ให้สร้างรายงานว่าไม่มีการเปลี่ยนแปลง"
✅ Test Task แบบ Manual ก่อนตั้ง Schedule
