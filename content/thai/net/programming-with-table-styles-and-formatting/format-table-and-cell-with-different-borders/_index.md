---
title: จัดรูปแบบตารางและเซลล์ด้วยเส้นขอบที่ต่างกัน
linktitle: จัดรูปแบบตารางและเซลล์ด้วยเส้นขอบที่ต่างกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการจัดรูปแบบตารางและเซลล์ที่มีเส้นขอบต่างกันโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อจัดรูปแบบตารางและเซลล์ที่มีเส้นขอบต่างกันโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีใช้เส้นขอบแบบกำหนดเองกับตารางและเซลล์เฉพาะในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 3: เริ่มตารางใหม่และเพิ่มเซลล์
ในการเริ่มสร้างตาราง เราใช้`StartTable()` วิธีการของตัวสร้างเอกสาร จากนั้นเราจะเพิ่มเซลล์ลงในตารางโดยใช้`InsertCell()` วิธีการและเราเขียนเนื้อหาของเซลล์ไปยังการใช้`Writeln()` วิธี.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// กำหนดเส้นขอบให้ทั้งตาราง
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// ตั้งค่าช่องว่างภายในสำหรับเซลล์นี้
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// ระบุช่องว่างภายในเซลล์อื่นสำหรับเซลล์ที่สอง
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// ล้างการจัดรูปแบบเซลล์จากการดำเนินการก่อนหน้า
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// สร้างเส้นขอบที่หนาขึ้นสำหรับเซลล์แรกในแถวนี้ มันจะแตกต่างออกไป
// สัมพันธ์กับเส้นขอบที่กำหนดไว้สำหรับตาราง
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

  แก้ไขเพิ่มเติม
สุดท้ายให้บันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

ขอแสดงความยินดี! ขณะนี้คุณได้จัดรูปแบบตารางและเซลล์ที่มีเส้นขอบต่างกันโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับจัดรูปแบบตารางและเซลล์ที่มีเส้นขอบต่างกันโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//กำหนดเส้นขอบให้ทั้งตาราง
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// ตั้งค่าการแรเงาเซลล์สำหรับเซลล์นี้
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// ระบุเฉดสีของเซลล์อื่นสำหรับเซลล์ที่สอง
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// ล้างการจัดรูปแบบเซลล์จากการดำเนินการก่อนหน้า
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// สร้างเส้นขอบให้ใหญ่ขึ้นสำหรับเซลล์แรกของแถวนี้ สิ่งนี้จะแตกต่างออกไป
	// เมื่อเทียบกับเส้นขอบที่กำหนดไว้สำหรับตาราง
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดรูปแบบตารางและเซลล์ที่มีเส้นขอบที่แตกต่างกันโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถปรับแต่งเส้นขอบตารางและเซลล์ในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและตอบสนองความต้องการเฉพาะได้