# CLAUDE.md — Working Memory สำหรับโปรเจกต์

## วิธีใช้งาน
วางไฟล์นี้ในโฟลเดอร์ทำงานของคุณ
Claude จะอ่านไฟล์นี้ก่อนทำงานทุกครั้ง

---

# Project: [ชื่อโครงการ]

## Context
[อธิบายบริบทการทำงาน 3-5 ประโยค]

## Working Files
- `data/` — ข้อมูล Raw
- `reports/` — รายงานที่สร้างแล้ว
- `templates/` — Template ต่างๆ

## Naming Convention
- ไฟล์รายงาน: `YYYY-MM_report_[topic].docx`
- ข้อมูล: `YYYY-MM_data_[source].csv`
- บันทึก: `YYYY-MM-DD_notes_[topic].md`

## Do NOT
- อย่าแก้ไขไฟล์ใน `archive/`
- อย่า commit ไฟล์ที่มี "DRAFT" ในชื่อ

## Current Priority
[ระบุงานที่กำลังทำอยู่]
