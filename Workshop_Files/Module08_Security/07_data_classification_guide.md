# Data Classification Guide สำหรับการใช้งาน AI

## Level 1: PUBLIC 🟢
ข้อมูลที่เผยแพร่ต่อสาธารณะได้
- ข่าวประชาสัมพันธ์
- ข้อมูลสินค้าบนเว็บไซต์
- เอกสารนโยบายทั่วไป

→ ✅ ส่งให้ AI ได้เลย

## Level 2: INTERNAL 🟡
ข้อมูลภายในองค์กร
- รายงานประชุม
- แผนงานโครงการ
- ข้อมูลพนักงาน (ชื่อ-นามสกุล, แผนก)

→ ⚠️ ส่งได้แต่ต้องระวัง อย่า Share ออกภายนอก

## Level 3: CONFIDENTIAL 🔴
ข้อมูลความลับทางธุรกิจ
- ข้อมูลลูกค้า (PII)
- ข้อมูลการเงิน Detailed
- Trade Secrets
- Passwords / API Keys

→ ❌ ไม่ควรส่งให้ AI โดยตรง
   ✅ Anonymize ก่อนส่ง หรือใช้ On-premise AI เท่านั้น

## Level 4: RESTRICTED 🔴🔴
ข้อมูลกฎหมาย / Compliance
- ข้อมูลสุขภาพ (PDPA)
- ข้อมูลการเงินส่วนบุคคล
- Legal Privileged Documents

→ ❌ ห้ามส่งให้ AI Cloud ทุกกรณี
   ⚠️ ต้องปรึกษา Legal และ DPO ก่อน
