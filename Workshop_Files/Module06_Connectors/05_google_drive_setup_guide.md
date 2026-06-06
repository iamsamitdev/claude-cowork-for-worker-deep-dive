# คู่มือตั้งค่า Google Drive Connector

## ขั้นตอนการเชื่อมต่อ

### Step 1: เปิดใช้งาน Connector
1. เปิด Claude Desktop App
2. ไปที่ Settings → Connectors / Integrations
3. ค้นหา "Google Drive"
4. คลิก "Connect"

### Step 2: Authentication
1. เข้าสู่ Google Account ของคุณ
2. อนุญาต Permission ที่ Claude ขอ:
   - อ่านไฟล์ใน Drive ✓
   - สร้างและแก้ไขไฟล์ ✓ (ถ้าต้องการ)
3. Copy Authorization Code กลับมาใน Claude

### Step 3: ทดสอบการเชื่อมต่อ
พิมพ์: "รายการไฟล์ 10 ไฟล์ล่าสุดใน Google Drive ของฉัน"

---

## Use Cases — Google Drive

### 1. อ่านเอกสาร
"อ่านไฟล์ 'Sales Report Q1.docx' ใน Drive แล้วสรุปให้หน่อย"

### 2. ค้นหาไฟล์
"หาไฟล์ทั้งหมดที่มีคำว่า 'budget' ใน Drive ของฉัน"

### 3. สร้างไฟล์ใหม่
"สร้าง Google Doc ชื่อ 'Meeting Notes April 2569' 
ใน Folder /Meetings/2569/ พร้อมเนื้อหาต่อไปนี้: [เนื้อหา]"

### 4. Daily Briefing จาก Drive
"ทุกเช้า อ่านไฟล์ใน Drive ที่แก้ไขล่าสุด 24 ชั่วโมงที่ผ่านมา
แล้วสรุปให้ฉันทราบว่ามีอะไรเปลี่ยนแปลงบ้าง"

---

## Troubleshooting
- Token หมดอายุ: Re-authenticate ทุก 30 วัน
- Permission Error: ตรวจสอบ Scope ที่อนุมัติ
- ไม่พบไฟล์: ตรวจสอบว่าไฟล์ใน Shared Drive หรือ My Drive
