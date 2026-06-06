# AI Activity Audit Log — Template

## วิธีใช้งาน
บันทึกทุกครั้งที่ Claude ทำงานสำคัญ
เก็บไว้ใน ai_audit_log.csv

---

## Columns

| Column | คำอธิบาย | ตัวอย่าง |
|--------|---------|---------|
| Date | วันที่ | 2569-04-01 |
| User | ผู้ใช้งาน | somchai@company.com |
| Task | งานที่ทำ | สรุปรายงาน Q1 |
| Data Used | ข้อมูลที่ใช้ | sales_report.csv |
| Output | ผลลัพธ์ | summary.md |
| Reviewed | Review แล้วไหม | ✅ Yes |
| Notes | หมายเหตุ | - |

---

## ตัวอย่าง Log

Date,User,Task,Data Used,Output,Reviewed,Notes
2569-04-01,somchai,สรุปรายงาน,sales_q1.csv,summary.md,Yes,ผลถูกต้อง
2569-04-02,vipa,สร้าง Excel,budget.csv,budget_tracker.xlsx,Yes,ตรวจสอบ formula แล้ว
2569-04-03,thanat,อ่าน Email,inbox (Gmail),email_digest.md,Yes,ไม่มีการส่ง email

---

## Prompt สำหรับ Claude ช่วย Log

"บันทึกลงใน ai_audit_log.csv ว่า:
วันที่: [วันนี้]
ผู้ใช้: [ชื่อ]
งาน: [สิ่งที่ทำ]
ข้อมูลที่ใช้: [ไฟล์]
Output: [ไฟล์ที่สร้าง]"
