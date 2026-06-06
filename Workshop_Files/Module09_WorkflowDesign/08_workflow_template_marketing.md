# Workflow Template: Marketing Team

## Workflow 1: Content Brief → Draft
Trigger: On Demand
Input: content_brief.md
Process: สร้าง Draft บทความ/Post
Output: content_draft.md

Prompt:
```
อ่าน content_brief.md แล้วสร้าง Draft บทความ:
- ความยาว: [ระบุ]
- Tone: [Professional/Casual/Educational]
- Platform: [Blog/LinkedIn/Facebook/Email]
- Target Audience: [ระบุ]
- Call to Action: [ระบุ]

สร้าง 2 Version: Version A (Formal) และ Version B (Casual)
```

---

## Workflow 2: Campaign Performance Report
Trigger: ทุกสิ้นเดือน
Input: campaign_data.csv
Process: วิเคราะห์ KPIs, สรุป insights
Output: campaign_report_MM.docx

Prompt:
```
อ่าน campaign_data.csv ที่มีข้อมูล:
Impressions, Clicks, CTR, Conversions, Cost, Revenue

สร้าง Word Document ชื่อ campaign_report_[เดือน].docx:
1. Executive Summary
2. KPI Performance vs Target (ตาราง)
3. Best Performing Campaign
4. Budget Efficiency (ROI %)
5. Recommendations for Next Month
```
