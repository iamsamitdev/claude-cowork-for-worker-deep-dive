# Prompt Library: Financial Statement Analysis ด้วย Claude

## ชุดที่ 1 — อ่านและสรุปงบการเงิน

### Prompt 1: สรุปภาพรวมการเงิน
```
อ่านไฟล์ 04_financial_statement_q1q4.csv และสรุปภาพรวมผลประกอบการ:
1. รายได้รวมทั้งปี 2025
2. กำไรสุทธิรวมทั้งปี 2025
3. Quarter ที่ทำกำไรสูงสุดและต่ำสุด
4. แนวโน้มโดยรวม (เติบโต / ทรงตัว / ลดลง)
ตอบเป็นภาษาไทย ความยาวไม่เกิน 5 บรรทัด
```

### Prompt 2: คำนวณ Financial Ratios
```
จากข้อมูลในไฟล์ 04_financial_statement_q1q4.csv คำนวณ:
1. Gross Profit Margin (%) ทุก Quarter
2. Net Profit Margin (%) ทุก Quarter
3. Current Ratio ทุก Quarter
4. Return on Equity (ROE) ทุก Quarter

แสดงผลเป็นตาราง และบอกว่า Ratio ไหนที่น่าเป็นห่วง พร้อมเหตุผล
```

---

## ชุดที่ 2 — วิเคราะห์ Trend

### Prompt 3: Revenue Trend Analysis
```
วิเคราะห์แนวโน้มรายได้จากข้อมูล Q1-Q4 2025:
- รายได้เติบโตกี่ % จาก Q1 ถึง Q4?
- Quarter ไหนมี Growth สูงสุด?
- คาดการณ์รายได้ Q1 2026 ถ้าแนวโน้มคงที่
แสดงการคำนวณและข้อสรุป
```

### Prompt 4: Cost Structure Analysis
```
วิเคราะห์โครงสร้างต้นทุนจากไฟล์ financial_statement:
- Cost of Goods Sold คิดเป็น % ของ Revenue แต่ละ Quarter
- Operating Expenses เปลี่ยนแปลงอย่างไร?
- บอกว่าบริษัทนี้ควร Focus ที่ Cost Control ส่วนไหน
```

---

## ชุดที่ 3 — สร้าง Management Report

### Prompt 5: Executive Summary
```
สร้าง Executive Summary สำหรับผู้บริหารจากข้อมูล Financial Statement:
- ความยาว: 1 หน้า A4
- โครงสร้าง: Highlights → Risks → Recommendations
- ภาษา: ภาษาไทย เป็นทางการ
- รวม Key Metrics Table ด้านบน
```

### Prompt 6: Financial Narrative (Board Meeting)
```
เตรียม Financial Narrative สำหรับนำเสนอใน Board Meeting:
- เริ่มด้วยประโยคสรุปที่กระชับ 1 ประโยค
- อธิบาย Performance Q4 เทียบ Q3
- ระบุ 3 จุดแข็งและ 2 ความเสี่ยง
- จบด้วย Recommendation 3 ข้อ
รูปแบบ: Bullet Points สำหรับ Presentation
```

---

## ชุดที่ 4 — Variance Analysis

### Prompt 7: Quarter-over-Quarter Comparison
```
เปรียบเทียบผลประกอบการ Q3 vs Q4 2025:
สร้างตาราง Variance Analysis แสดง:
- ตัวเลข Q3, Q4, และ Variance (จำนวน + %)
- บรรทัดสีแดงสำหรับ Metric ที่แย่ลง
- Comment สั้นๆ อธิบายสาเหตุที่เป็นไปได้
```

### Prompt 8: Annual Performance vs Industry Benchmark
```
สมมุติว่า Industry Benchmark คือ:
- Gross Margin: 35%, Net Margin: 12%, Current Ratio: 2.0
เปรียบเทียบผลประกอบการบริษัทนี้กับ Benchmark ในแต่ละ Quarter
บอกว่า Quarter ไหนที่ "Beat" / "Miss" / "In Line" กับ Benchmark
```

---

## Tips การใช้ Prompt เหล่านี้

1. **เพิ่ม Context** — บอก Industry หรือขนาดบริษัทเพื่อให้ Claude วิเคราะห์ได้แม่นยำขึ้น
2. **ระบุ Audience** — "สำหรับผู้บริหาร" vs "สำหรับนักลงทุน" จะได้ภาษาและ Focus ต่างกัน
3. **Iterate** — ถ้าผลลัพธ์ไม่ถูกใจ ให้บอก Claude ว่าต้องการปรับอะไร
4. **Verify ตัวเลข** — ตรวจสอบการคำนวณด้วยมือเสมอก่อนนำเสนอ
