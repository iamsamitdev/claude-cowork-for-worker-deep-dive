# คู่มือตั้งค่า Context ใน Claude Cowork

## ทำไมต้องตั้งค่า Context?

Claude ไม่รู้จักองค์กรของคุณโดยอัตโนมัติ
การตั้งค่า Context ช่วยให้:
- Claude ใช้ภาษาและ Format ที่คุณต้องการ
- ไม่ต้องอธิบายซ้ำทุกครั้ง
- ผลลัพธ์ตรงกับ Standard ขององค์กร

## วิธีที่ 1: CLAUDE.md (แนะนำ)

สร้างไฟล์ `CLAUDE.md` ในโฟลเดอร์ทำงาน
Claude จะอ่านไฟล์นี้ทุกครั้งที่เริ่มทำงาน

ใช้ template จากไฟล์ `02_claude_md_template.md`

## วิธีที่ 2: System Prompt

ใน Claude Desktop App ไปที่ Settings
เพิ่ม Custom Instructions สำหรับ Cowork Mode

## วิธีที่ 3: Project Memory

บอก Claude ให้จำข้อมูลในการสนทนา:
"จำไว้ว่า: ฉันทำงานที่บริษัท ABC ตำแหน่ง Sales Manager
ทุกรายงานต้องเป็นภาษาไทย formal style"

## Best Practices

1. อัปเดต CLAUDE.md เมื่อโครงการเปลี่ยน
2. ระบุสิ่งที่ไม่ต้องการชัดเจน
3. ระบุ Output format ที่ต้องการ
4. บอก Audience ของเอกสาร
