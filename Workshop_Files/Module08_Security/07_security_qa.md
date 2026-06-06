# Q&A: Security & Safety

## คำถามพบบ่อย

**Q: Claude เก็บข้อมูลของฉันไหม?**
A: Anthropic มี Privacy Policy ที่ชัดเจน ข้อมูลใน Cowork Mode 
   ไม่ถูกนำไป Train Model โดยค่า default
   แนะนำอ่าน Privacy Policy ที่ anthropic.com/privacy

**Q: ถ้า Claude ทำผิดพลาด ใครรับผิดชอบ?**
A: ผู้ใช้ยังคงรับผิดชอบ Output ทุกอย่าง
   Claude เป็น Tool ไม่ใช่ Decision Maker

**Q: ข้อมูลใน CLAUDE.md ปลอดภัยไหม?**
A: CLAUDE.md อยู่ในเครื่องของคุณ ไม่ได้ส่งออกไปที่ไหน
   แต่ Claude จะ Include ใน Context ทุกครั้งที่ทำงาน

**Q: Connector อย่าง Gmail/Slack ปลอดภัยไหม?**
A: Connector ใช้ OAuth มาตรฐาน
   แนะนำ: Start with Read-only, Review permissions ทุกเดือน

**Q: ถ้าพบว่า Claude ทำสิ่งที่ไม่ได้สั่งทำอย่างไร?**
A: 
1. หยุดทำงานทันที (ปิดการสนทนา)
2. ตรวจสอบว่ามีการ Action อะไรไปแล้วบ้าง
3. Undo ถ้าทำได้ (ลบไฟล์ที่สร้าง, Recall email)
4. แจ้ง IT Security
5. Report ไปที่ Anthropic (thumbs down + feedback)

**Q: ควรใช้ Claude กับข้อมูลลูกค้าได้ไหม?**
A: ถ้าข้อมูลมี PII ต้อง Anonymize ก่อน
   เช่น แทน "นายสมชาย วิลัย, 0812345678" ด้วย "Customer A, Phone: [REDACTED]"
