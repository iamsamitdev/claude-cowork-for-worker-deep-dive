# Security Guidelines — การใช้ AI อย่างปลอดภัยในองค์กร

## หลักการ 5 ข้อ

### 1. Least Privilege
ให้ Claude เข้าถึงเฉพาะสิ่งที่จำเป็น
❌ ให้ Access โฟลเดอร์ทั้งเครื่อง
✅ ให้ Access เฉพาะโฟลเดอร์โครงการที่ทำงานอยู่

### 2. Human-in-the-Loop
ขั้นตอนสำคัญต้องมีคนอนุมัติ
❌ ให้ Claude ส่ง Email โดยอัตโนมัติ
✅ Claude Draft → คุณ Review → คุณ ส่ง

### 3. Data Classification
ข้อมูลบางประเภทไม่ควรส่งให้ AI:
- 🔴 ห้าม: รหัสผ่าน, Private Key, ข้อมูลบัตรเครดิต
- 🟡 ระวัง: ข้อมูลส่วนตัวลูกค้า, ข้อมูลทางการแพทย์
- 🟢 โอเค: ข้อมูลทั่วไป, Draft ที่ไม่มี PII

### 4. Audit Trail
บันทึกสิ่งที่ Claude ทำ
- Log การเข้าถึงไฟล์
- เก็บ History ของ Task ที่รัน
- Review ทุก 30 วัน

### 5. Regular Review
- ทบทวน Permissions ทุก 30 วัน
- Revoke ที่ไม่ใช้แล้ว
- อัปเดต Security Policy เมื่อมีการเปลี่ยนแปลง
