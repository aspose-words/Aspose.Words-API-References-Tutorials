---
title: ตารางที่จัดรูปแบบแล้ว
linktitle: ตารางที่จัดรูปแบบแล้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางที่จัดรูปแบบในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/formatted-table/
---

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีสร้างตารางที่จัดรูปแบบในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถสร้างตารางที่มีการจัดรูปแบบแบบกำหนดเองในเอกสาร Word ของคุณโดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและการเริ่มต้นตัวสร้างเอกสาร
เพื่อเริ่มสร้างตารางที่จัดรูปแบบแล้ว เราจำเป็นต้องสร้างเอกสารใหม่และเริ่มต้นตัวสร้างเอกสาร ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//สร้างเอกสารและเริ่มต้นตัวสร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: สร้างตารางที่จัดรูปแบบ
ต่อไป เราจะสร้างตารางที่จัดรูปแบบโดยใช้วิธีการที่ได้รับจากตัวสร้างเอกสาร ใช้รหัสต่อไปนี้:

```csharp
// เริ่มต้นการสร้างอาร์เรย์
Table table = builder. StartTable();

// การสร้างแถวส่วนหัวของตาราง
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// การสร้างตัวอาร์เรย์
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// สิ้นสุดการสร้างอาร์เรย์
builder. EndTable();
```

 ที่นี่เราใช้ตัวสร้างเอกสารเพื่อสร้างตารางทีละขั้นตอน เราเริ่มต้นด้วยการโทร`StartTable()` เพื่อเริ่มต้นตาราง แล้วเราก็ใช้`InsertCell()` เพื่อแทรกเซลล์และ`Write()` เพื่อเพิ่มเนื้อหาลงในแต่ละเซลล์ นอกจากนี้เรายังใช้คุณสมบัติการจัดรูปแบบที่แตกต่างกันเพื่อกำหนดการจัดรูปแบบของแถวตาราง เซลล์ และข้อความ

## ขั้นตอนที่ 4: บันทึกเอกสาร
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่มีตารางที่จัดรูปแบบแล้ว ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับตารางที่จัดรูปแบบโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// ต้องใช้การจัดรูปแบบทั้งตารางหลังจากมีอย่างน้อยหนึ่งแถวในตาราง
	table.LeftIndent = 20.0;
	// ตั้งค่าความสูงและกำหนดกฎความสูงสำหรับแถวส่วนหัว
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// เราไม่จำเป็นต้องระบุความกว้างของเซลล์นี้เนื่องจากสืบทอดมาจากเซลล์ก่อนหน้า
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// รีเซ็ตความสูงและกำหนดกฎความสูงอื่นสำหรับเนื้อหาของตาราง
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// รีเซ็ตการจัดรูปแบบตัวอักษร
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างตารางที่จัดรูปแบบในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถสร้างตารางแบบกำหนดเองพร้อมการจัดรูปแบบเฉพาะในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสามารถนำเสนอและจัดโครงสร้างข้อมูลของคุณในลักษณะที่ดึงดูดสายตาและจัดระเบียบได้