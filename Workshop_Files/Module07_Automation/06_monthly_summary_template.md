# Template: Monthly Summary

## Prompt

```
ชื่อ Task: Monthly Business Summary
Trigger: ทุกวันที่ 28 เวลา 09:00 น.

งาน:
1. รวบรวม weekly_report_*.md ทั้งหมดของเดือนนี้
2. อ่านข้อมูล KPI จาก kpi_tracker.csv (ถ้ามี)
3. อ่าน customer_feedback ของเดือนนี้ (ถ้ามี)

สร้างไฟล์: monthly_summary_YYYY-MM.md
โครงสร้าง:

# รายงานประจำเดือน [เดือน/ปี]

## Executive Summary
[3-5 ประโยคสรุปภาพรวม]

## KPI Summary
[ตารางเป้าหมาย vs ผลจริง]

## Highlights
[Top 3 ความสำเร็จ]

## Challenges
[ปัญหาที่พบและวิธีแก้]

## Outlook เดือนหน้า
[แผนและเป้าหมาย]
```
