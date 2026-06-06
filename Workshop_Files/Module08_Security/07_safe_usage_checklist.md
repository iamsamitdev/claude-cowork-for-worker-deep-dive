# Safe AI Usage Checklist

## ก่อนเริ่มงาน
- [ ] ตรวจสอบว่า Data ที่จะส่งให้ Claude ไม่มีข้อมูลลับ
- [ ] ตั้งค่า Working Directory ให้แคบพอ (ไม่ได้ทั้ง Drive)
- [ ] Review CLAUDE.md ว่า Instruction ถูกต้อง

## ระหว่างทำงาน
- [ ] ติดตาม Actions ที่ Claude ทำ
- [ ] หยุดถ้า Claude ทำสิ่งที่ไม่ได้สั่ง
- [ ] ไม่อนุมัติ Actions ที่ไม่เข้าใจ

## ก่อน Output ใช้งานจริง
- [ ] ตรวจสอบเนื้อหาถูกต้อง
- [ ] ตรวจสอบว่าไม่มีข้อมูลที่ไม่ควรอยู่ในเอกสาร
- [ ] Review Output ที่จะส่งออกภายนอก

## ประจำเดือน
- [ ] Review Connector Permissions
- [ ] ตรวจสอบ Scheduled Tasks ที่ยังรันอยู่
- [ ] อ่าน Log ของ Claude Activities
- [ ] Revoke Permissions ที่ไม่ใช้แล้ว
