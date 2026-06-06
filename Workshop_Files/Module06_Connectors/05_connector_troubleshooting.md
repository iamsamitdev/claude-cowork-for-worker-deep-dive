# Troubleshooting Guide — Connectors

## Google Drive / Gmail ปัญหาที่พบบ่อย

### Error: "Authorization failed"
แก้: ไปที่ Settings → Connectors → Disconnect แล้ว Re-connect ใหม่

### Error: "File not found"
ตรวจสอบ:
- ไฟล์อยู่ใน My Drive หรือ Shared Drive?
- ชื่อไฟล์ถูกต้องไหม (case-sensitive)?
- มี Permission เข้าถึงไฟล์นั้นไหม?

### Error: "Quota exceeded"
แก้: รอ 24 ชั่วโมง Google API มี Rate Limit

---

## Slack ปัญหาที่พบบ่อย

### ไม่เห็น Private Channels
แก้: ต้องเพิ่ม Bot ไปใน Channel ก่อน: /invite @claude-bot

### Messages ไม่อัปเดต Real-time
ปกติ: Claude อ่านข้อมูล ณ เวลาที่ถาม ไม่ใช่ Real-time stream

---

## General Tips

1. Token หมดอายุ: Re-authenticate ทุก 30 วัน
2. ทดสอบใน Test Environment ก่อน Production
3. Log การใช้งาน Connector ไว้เสมอ
4. ถ้า Error ไม่ชัดเจน: Disconnect แล้ว Connect ใหม่
