# แบบฝึกหัด: สร้าง Sales Dashboard ด้วย Claude

## โจทย์
ใช้ข้อมูลจากไฟล์ `03_sales_data_raw.csv` สร้าง Excel Dashboard

## Prompt ที่ใช้

```
อ่านไฟล์ 03_sales_data_raw.csv แล้วสร้างไฟล์ Excel ชื่อ sales_dashboard.xlsx 
ที่ประกอบด้วย:

Sheet 1 - Raw Data: ข้อมูลดิบทั้งหมด (format ตาราง สวยงาม)

Sheet 2 - Monthly Summary:
- ยอดขายรวมแต่ละเดือน
- เปรียบเทียบ MoM Growth %
- Chart: Bar chart ยอดขายรายเดือน

Sheet 3 - Product Analysis:
- ยอดขายแต่ละสินค้า
- % สัดส่วนตลาด
- Chart: Pie chart

Sheet 4 - KPI Dashboard:
- ยอดขายรวม Q1
- สินค้าขายดีสุด
- พนักงานขายยอดเยี่ยม
- ภาคที่ทำยอดสูงสุด
```

## สิ่งที่คาดหวัง
- [ ] ไฟล์ Excel เปิดได้ปกติ
- [ ] มีครบ 4 Sheet
- [ ] Chart แสดงผลถูกต้อง
- [ ] ตัวเลขตรงกับข้อมูล Raw
