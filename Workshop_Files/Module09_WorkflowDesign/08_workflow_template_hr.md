# Workflow Template: HR Team

## Workflow 1: CV Screening Summary
Trigger: On Demand (เมื่อได้รับ CV batch)
Input: CV files (PDF/Word)
Process: อ่าน CV ทั้งหมด, เปรียบเทียบกับ JD
Output: cv_screening_summary.xlsx

Prompt:
```
อ่าน JD จากไฟล์ job_description.md
แล้วอ่าน CV ทั้งหมดในโฟลเดอร์ cvs/
สร้าง Excel ชื่อ cv_screening.xlsx ที่มี:
- ชื่อผู้สมัคร, ประสบการณ์, ทักษะหลัก
- ตรงกับ JD กี่ข้อ (จากทั้งหมดกี่ข้อ)
- Recommendation: Shortlist / Maybe / Pass
- เหตุผลสั้นๆ
```

---

## Workflow 2: Employee Survey Analysis
Trigger: Monthly (หลังปิด Survey)
Input: survey_results.csv
Process: วิเคราะห์ themes, sentiment
Output: survey_analysis_MM.md

Prompt:
```
อ่าน survey_results.csv 
วิเคราะห์:
1. Overall Sentiment Score
2. Top 3 Positive Themes
3. Top 3 Improvement Areas
4. Verbatim Quotes ที่สำคัญ (5 ข้อ)
5. แนะนำ Action 3 ข้อที่ควรทำภายใน 30 วัน
```
