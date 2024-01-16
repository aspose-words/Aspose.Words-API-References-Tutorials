---
title: แทรกตารางโดยตรง
linktitle: แทรกตารางโดยตรง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกตารางลงในเอกสาร Word โดยตรงด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/insert-table-directly/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแทรกตารางลงในเอกสาร Word โดยตรงโดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแทรกตารางลงในเอกสาร Word ของคุณได้โดยตรงโดยทางโปรแกรม

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและตาราง
ในการเริ่มการประมวลผลคำด้วยอาร์เรย์ เราจำเป็นต้องสร้างเอกสารใหม่และเริ่มต้นอาร์เรย์ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();

//สร้างอาร์เรย์
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การสร้างอาร์เรย์
ต่อไป เราจะสร้างตารางโดยการเพิ่มแถวและเซลล์ ใช้รหัสต่อไปนี้เป็นตัวอย่าง:

```csharp
// สร้างแถวแรก
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// สร้างเซลล์แรก
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// ทำซ้ำเซลล์สำหรับเซลล์ที่สองในแถว
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 ที่นี่เราสร้างแถวด้วย`AllowBreakAcrossPages` คุณสมบัติที่กำหนดเป็น`true` เพื่อให้สามารถแบ่งหน้าระหว่างแถวได้ จากนั้นเราสร้างเซลล์ที่มีพื้นหลังเป็นสี ความกว้างคงที่ และเนื้อหาข้อความที่ระบุ จากนั้นเราจะทำซ้ำเซลล์นี้เพื่อสร้างเซลล์ที่สองในแถว

## ขั้นตอนที่ 4: ปรับตารางให้พอดีอัตโนมัติ
เราสามารถใช้การปรับอัตโนมัติกับตารางเพื่อจัดรูปแบบให้ถูกต้องได้ ใช้รหัสต่อไปนี้:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

บรรทัดโค้ดนี้ใช้การปรับให้พอดีอัตโนมัติตามความกว้างของคอลัมน์คงที่

## ขั้นตอนที่ 5: การลงทะเบียน

  เอกสารที่แก้ไข
สุดท้าย เราต้องบันทึกเอกสารที่แก้ไขโดยแทรกตารางโดยตรง ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกตารางโดยตรงโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// เราเริ่มต้นด้วยการสร้างวัตถุตาราง โปรดทราบว่าเราต้องส่งวัตถุเอกสาร
	//ไปยังตัวสร้างของแต่ละโหนด เนื่องจากทุกโหนดที่เราสร้างจะต้องเป็นของตัวเอง
	// ไปยังเอกสารบางอย่าง
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// ที่นี่เราสามารถเรียก SureMinimum เพื่อสร้างแถวและเซลล์ให้เราได้ วิธีนี้ใช้
	// เพื่อให้แน่ใจว่าโหนดที่ระบุนั้นถูกต้อง ในกรณีนี้ ตารางที่ถูกต้องควรมีอย่างน้อยหนึ่งแถวและหนึ่งเซลล์
	// แต่เราจะจัดการสร้างแถวและตารางเองแทน
	// นี่จะเป็นวิธีที่ดีที่สุดหากเราสร้างตารางภายในอัลกอริทึม
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// ตอนนี้เราสามารถใช้การตั้งค่าการปรับให้พอดีอัตโนมัติได้แล้ว
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// จากนั้นเราจะทำซ้ำขั้นตอนนี้กับเซลล์และแถวอื่นๆ ในตาราง
	// นอกจากนี้เรายังสามารถเร่งความเร็วได้ด้วยการโคลนเซลล์และแถวที่มีอยู่
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแทรกตารางลงในเอกสาร Word โดยตรงโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถแทรกตารางลงในเอกสาร Word ของคุณได้โดยตรงโดยทางโปรแกรม คุณลักษณะนี้ช่วยให้คุณสร้างและปรับแต่งตารางได้ตามความต้องการเฉพาะของคุณ