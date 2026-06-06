# Checklist ก่อน Deploy Automation

## ✅ Pre-deployment

### Design
- [ ] มี Workflow Canvas กรอกครบแล้ว
- [ ] ทดสอบ Prompt แบบ Manual แล้วได้ผลที่ต้องการ
- [ ] กำหนด Output Format ชัดเจน
- [ ] มี Error Handling

### Permissions
- [ ] Claude มีสิทธิ์เข้าถึง Input Files/Connectors
- [ ] Output Folder มีอยู่แล้วและ Claude เขียนได้
- [ ] ไม่มีข้อมูล Sensitive ที่ไม่ควร Process อัตโนมัติ

### Testing
- [ ] Run ครั้งแรกแบบ Manual เพื่อตรวจสอบ
- [ ] ตรวจสอบ Output ว่าถูกต้อง
- [ ] ทดสอบ Error Case (ไม่มีไฟล์ / ไฟล์เสีย)

## ✅ Post-deployment
- [ ] Monitor ผลลัพธ์ 1 สัปดาห์แรก
- [ ] ตั้งวันที่ Review: ___________
- [ ] Document ว่า Workflow ทำอะไร
