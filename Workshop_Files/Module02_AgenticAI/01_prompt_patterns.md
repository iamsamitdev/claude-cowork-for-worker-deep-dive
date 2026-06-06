# Prompt Patterns สำหรับ Agentic Tasks

## Pattern 1: Task Decomposition
สำหรับงานซับซ้อน ระบุ Steps ชัดเจน

```
ช่วยทำสิ่งต่อไปนี้ตามลำดับ:
1. [Step 1]
2. [Step 2]
3. [Step 3]
Output: [บอก format ที่ต้องการ]
```

## Pattern 2: Context + Task + Format
บอก Context → งาน → รูปแบบผลลัพธ์

```
Context: ฉันเป็น [ตำแหน่ง] ต้องการ [เป้าหมาย]
Task: [อธิบายงาน]
Output Format: [ไฟล์ Excel / Word / สรุปแบบ bullet / ตาราง]
```

## Pattern 3: Constraint-based
ระบุข้อจำกัดและสิ่งที่ไม่ต้องการ

```
[อธิบายงาน]
ข้อกำหนด:
- ความยาว: ไม่เกิน 1 หน้า A4
- ภาษา: ภาษาไทย
- ไม่ต้องรวม: [สิ่งที่ไม่ต้องการ]
```

## Pattern 4: Iterative Refinement
สำหรับงานที่ต้องปรับปรุงหลายรอบ

```
สร้าง [ผลลัพธ์] ฉบับร่างก่อน
จากนั้นถามฉันว่าต้องการปรับอะไรก่อน Finalize
```

## Pattern 5: Batch Processing
สำหรับงานที่ทำซ้ำหลายไฟล์

```
ทำ [Action] กับไฟล์ทุกไฟล์ที่มีนามสกุล .csv ในโฟลเดอร์ [folder]
สร้าง Summary รวมใน [output_file]
```
