# Workflow Template: Operations / Admin

## Workflow 1: Meeting Minutes
Trigger: On Demand (หลังประชุม)
Input: voice_notes.txt หรือ raw_notes.txt
Process: Format meeting minutes
Output: minutes_YYYYMMDD.docx

Prompt:
```
อ่านบันทึกการประชุมจากไฟล์ raw_notes.txt
สร้าง Word Document ชื่อ minutes_[วันที่].docx:

โครงสร้าง:
- หัวเรื่อง, วันที่, ผู้เข้าร่วม
- วาระการประชุม (Agenda)
- สรุปการอภิปรายแต่ละวาระ
- มติที่ประชุม (ถ้ามี)
- Action Items: ผู้รับผิดชอบ + Deadline
- วันประชุมครั้งถัดไป
```

---

## Workflow 2: Monthly Expense Reconciliation
Trigger: ทุกวันที่ 5
Input: expense_receipts.csv, budget_plan.xlsx
Process: Compare actual vs budget
Output: expense_reconciliation_MM.xlsx

Prompt:
```
อ่าน expense_receipts.csv (ค่าใช้จ่ายจริง)
และ budget_plan.xlsx (งบประมาณ)

สร้าง Excel ชื่อ reconciliation_[เดือน].xlsx:
Sheet 1: Budget vs Actual (ตาราง + %)
Sheet 2: Over-budget Items (พร้อมเหตุผลถ้ามี)
Sheet 3: Summary Chart
```
