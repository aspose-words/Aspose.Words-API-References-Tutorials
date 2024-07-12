---
title: สร้างโต๊ะอย่างมีสไตล์
linktitle: สร้างโต๊ะอย่างมีสไตล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการสร้างตารางด้วยสไตล์ที่กำหนดเองโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อสร้างตารางที่มีสไตล์โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีสร้างตารางด้วยสไตล์ที่กำหนดเองในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งที่คุณต้องการบันทึกเอกสาร Word ที่แก้ไขแล้ว แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และตัวสร้างเอกสาร
 ถัดไป คุณต้องสร้างอินสแตนซ์ใหม่ของ`Document` คลาสและตัวสร้างเอกสารสำหรับเอกสารนั้น

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: เริ่มตารางใหม่และแทรกเซลล์
 ในการเริ่มสร้างตาราง เราใช้`StartTable()` วิธีการสร้างเอกสาร จากนั้นเราจะแทรกเซลล์ลงในตารางโดยใช้`InsertCell()` วิธี.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## ขั้นตอนที่ 4: กำหนดสไตล์ของตาราง
 ตอนนี้เราสามารถกำหนดรูปแบบตารางโดยใช้`StyleIdentifier` คุณสมบัติ. ในตัวอย่างนี้ เรากำลังใช้สไตล์ "MediumShading1Accent1"

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## ขั้นตอนที่ 5: ใช้ตัวเลือกสไตล์กับตาราง
 เราสามารถระบุลักษณะที่ควรจัดรูปแบบตามสไตล์ได้โดยใช้`StyleOptions`คุณสมบัติของอาร์เรย์ ในตัวอย่างนี้ เราใช้ตัวเลือกต่อไปนี้: "FirstColumn", "RowBands" และ "FirstRow"

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## ขั้นตอนที่ 6: ปรับขนาดตารางโดยอัตโนมัติ
 หากต้องการปรับขนาดของอาร์เรย์โดยอัตโนมัติตามเนื้อหา เราใช้`AutoFit()` วิธีการด้วย`AutoFitBehavior.AutoFitToContents` พฤติกรรม.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## ขั้นตอนที่ 7: เพิ่มเนื้อหาลงในเซลล์
 ตอนนี้เราสามารถเพิ่มเนื้อหาลงในเซลล์โดยใช้`Writeln()`และ`InsertCell()` วิธีการสร้างเอกสาร ในตัวอย่างนี้ เราเพิ่มส่วนหัวสำหรับ "รายการ" และ "ปริมาณ (

kg)" และข้อมูลที่เกี่ยวข้อง

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## ขั้นตอนที่ 8: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจะบันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

ขอแสดงความยินดี! ตอนนี้คุณได้สร้างตารางสไตล์แบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET แล้ว

### ตัวอย่างซอร์สโค้ดสำหรับ Build Table With Style โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// เราต้องแทรกอย่างน้อยหนึ่งแถวก่อนจึงจะตั้งค่าการจัดรูปแบบตารางได้
	builder.InsertCell();
	// ตั้งค่าสไตล์ตารางที่ใช้ตามตัวระบุสไตล์เฉพาะ
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// ใช้คุณลักษณะที่ควรจัดรูปแบบตามสไตล์
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างตารางที่มีสไตล์โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถปรับแต่งสไตล์ของตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและตอบสนองความต้องการเฉพาะได้