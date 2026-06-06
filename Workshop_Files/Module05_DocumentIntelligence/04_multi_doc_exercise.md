# แบบฝึกหัด: Multi-Document Intelligence Sprint

## โจทย์
ใช้ Claude วิเคราะห์บันทึกการประชุม 5 ครั้ง และ Feedback 2 ไฟล์
สร้างรายงานสรุปภาพรวม Q1 + Early Q2

## Prompt ที่ใช้

```
อ่านไฟล์ทั้งหมดต่อไปนี้:
- 04_meeting_transcript_01.txt ถึง _05.txt (5 ไฟล์)
- 04_customer_feedback_q1.txt
- 04_customer_feedback_q2.txt

แล้วสร้างรายงาน executive_briefing.md ที่ประกอบด้วย:

1. KEY DECISIONS (ตลอด Q1-Q2 Early)
   - ตัดสินใจอะไรบ้าง? ใคร? วันที่?

2. ACTION ITEMS ทั้งหมด
   - จัดกลุ่มตามผู้รับผิดชอบ
   - Status ที่ทราบ

3. CUSTOMER INSIGHTS
   - Theme หลักจาก Feedback
   - Top 3 Issues ที่ต้องแก้ไขด่วน

4. RISKS & CONCERNS
   - ความเสี่ยงที่พบในการประชุม
   - ความเสี่ยงจาก Customer Feedback

5. RECOMMENDED NEXT ACTIONS
   - Top 5 สิ่งที่ควรทำในสัปดาห์หน้า
```

## เวลาที่ใช้
Claude: ประมาณ 30-60 วินาที
ถ้าทำเอง: ประมาณ 2-3 ชั่วโมง
