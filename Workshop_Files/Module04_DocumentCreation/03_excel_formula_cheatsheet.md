# Excel Formulas Cheat Sheet สำหรับ Workshop

## Formulas ที่ใช้บ่อย

### SUM & AVERAGE
=SUM(B2:B10) — รวมค่าในช่วง
=AVERAGE(B2:B10) — ค่าเฉลี่ย
=SUMIF(A:A,"กลาง",B:B) — รวมเฉพาะที่เงื่อนไขตรง

### เปรียบเทียบและ Growth
=(B2-A2)/A2*100 — % Growth
=IF(B2>A2,"เกินเป้า","ต่ำกว่าเป้า") — เงื่อนไข

### การค้นหา
=VLOOKUP(A2,Sheet2!A:C,2,0) — ค้นหาข้อมูลข้ามชีต
=INDEX(B:B,MATCH(A2,A:A,0)) — ค้นหาแบบ Advanced

### Format
=TEXT(A2,"#,##0") — จัดรูปแบบตัวเลข
=TEXT(A2,"0.0%") — แสดงเป็น %

## Prompt ที่ใช้กับ Claude
"สร้าง Excel ที่มี formula สำหรับ [งานที่ต้องการ]
อธิบาย formula แต่ละอันด้วยว่าทำอะไร"
