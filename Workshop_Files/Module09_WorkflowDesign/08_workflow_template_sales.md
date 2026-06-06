# Workflow Template: Sales Team

## Workflow 1: Daily Sales Briefing
Trigger: ทุกเช้า 8:30 น.
Input: Pipeline data (CRM export), Email inbox
Process: สรุป leads, follow-ups, meetings วันนี้
Output: daily_sales_brief.md

Prompt:
```
อ่านไฟล์ pipeline_today.csv และ email_unread.txt
สรุปสำหรับ Sales Team:
1. Follow-up ที่ต้องทำวันนี้ (เรียงตาม Priority)
2. Meeting ที่มีวันนี้
3. Deals ที่ใกล้ปิด (Stage = Negotiation+)
4. Alert: Deals ที่ไม่มีการ Update นาน 7+ วัน
```

---

## Workflow 2: Post-Meeting Notes
Trigger: On Demand (หลัง Meeting)
Input: Meeting notes (raw)
Process: Format, extract actions, update CRM
Output: meeting_summary_DATE.md + CRM update prompt

Prompt:
```
อ่านบันทึกการประชุมนี้:
[วาง notes ลงที่นี่]

สร้าง:
1. Meeting Summary (WHO, WHAT, WHEN format)
2. Action Items ตาราง (ใคร, อะไร, ภายในวันที่)
3. CRM Update: ข้อมูลอะไรที่ควร Update ใน Deal Record
```
