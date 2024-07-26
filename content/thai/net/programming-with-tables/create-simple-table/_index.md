---
title: สร้างตารางอย่างง่าย
linktitle: สร้างตารางอย่างง่าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางอย่างง่ายในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/create-simple-table/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีสร้างตารางอย่างง่ายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถสร้างตารางแบบกำหนดเองในเอกสาร Word ของคุณโดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและการเริ่มต้นตัวสร้างเอกสาร
ในการเริ่มสร้างตาราง เราจำเป็นต้องสร้างเอกสารใหม่และเริ่มต้นตัวสร้างเอกสาร ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//สร้างเอกสารและเริ่มต้นตัวสร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การสร้างอาร์เรย์
ต่อไป เราจะสร้างตารางโดยใช้วิธีการที่ได้รับจากตัวสร้างเอกสาร ใช้รหัสต่อไปนี้:

```csharp
// เริ่มต้นการสร้างอาร์เรย์
builder. StartTable();

// การก่อสร้างเซลล์แรกของแถวแรก
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// การก่อสร้างเซลล์ที่สองของแถวแรก
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// เรียกวิธีการต่อไปนี้เพื่อสิ้นสุดบรรทัดแรกและเริ่มต้นบรรทัดใหม่
builder. EndRow();

// การก่อสร้างเซลล์แรกของแถวที่สอง
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// การก่อสร้างห้องขังที่สองของแถวที่สอง
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// เรียกเมธอดถัดไปเพื่อสิ้นสุดบรรทัดที่สอง
builder. EndRow();

// แสดงว่าก่อสร้างโต๊ะเสร็จแล้ว
builder. EndTable();
```

 ที่นี่เราใช้ตัวสร้างเอกสารเพื่อสร้างตารางทีละขั้นตอน เราเริ่มต้นด้วยการโทร`StartTable()` เพื่อเริ่มต้นตารางแล้วใช้`InsertCell()` เพื่อแทรกเซลล์และ`Write()` เพื่อเพิ่มเนื้อหาลงในแต่ละเซลล์ เรายังใช้`EndRow()` เพื่อสิ้นสุดแถวและเริ่มแถวใหม่ ในที่สุดเราก็โทร`EndTable()` เพื่อแสดงว่าการก่อสร้างโต๊ะเสร็จสมบูรณ์แล้ว

## ขั้นตอนที่ 4: บันทึกเอกสาร
สุดท้ายเราก็ต้องประหยัด

  เอกสารที่มีตารางที่สร้างขึ้น ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับสร้างตารางอย่างง่ายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// เริ่มสร้างโต๊ะ
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// สร้างเซลล์ที่สอง
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// เรียกวิธีการต่อไปนี้เพื่อสิ้นสุดแถวและเริ่มแถวใหม่
	builder.EndRow();
	// สร้างเซลล์แรกของแถวที่สอง
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// สร้างเซลล์ที่สอง
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// สัญญาณว่าเราสร้างโต๊ะเสร็จแล้ว
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างตารางอย่างง่ายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถสร้างตารางแบบกำหนดเองในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสามารถจัดรูปแบบและจัดระเบียบข้อมูลของคุณในลักษณะที่มีโครงสร้างและชัดเจน