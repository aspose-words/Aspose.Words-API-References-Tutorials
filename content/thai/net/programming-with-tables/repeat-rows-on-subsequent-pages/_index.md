---
title: ทำซ้ำแถวในหน้าถัดไป
linktitle: ทำซ้ำแถวในหน้าถัดไป
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีทำซ้ำแถวของตารางในหน้าถัดไปในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีทำซ้ำแถวของตารางในหน้าถัดไปของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถระบุแถวที่จะทำซ้ำในหน้าถัดไปของตารางในเอกสาร Word ได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและการเริ่มต้นตัวสร้างเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำด้วยตัวสร้างเอกสารและเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();

// เริ่มต้นตัวสร้างเอกสาร
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: สร้างตารางด้วยแถวที่ซ้ำกัน
ต่อไป เราจะสร้างตารางที่มีแถวซ้ำกันในหน้าถัดไป ใช้รหัสต่อไปนี้:

```csharp
// จุดเริ่มต้นของตาราง
builder. StartTable();

// การกำหนดค่าพารามิเตอร์บรรทัดแรก (บรรทัดส่วนหัว)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//แทรกเซลล์แรกของแถวแรก
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// แทรกเซลล์ที่สองของแถวแรก
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// กำหนดค่าพารามิเตอร์ของบรรทัดต่อไปนี้
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// วนซ้ำเพื่อแทรกเซลล์ในแถวต่อไปนี้
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// ท้ายตาราง
builder. EndTable();
```

 ที่นี่เราใช้เครื่องมือสร้างเอกสารเพื่อสร้างตารางที่มีแถวส่วนหัวสองแถวและแถวข้อมูลหลายแถว ที่`RowFormat.HeadingFormat` พารามิเตอร์ใช้เพื่อทำเครื่องหมายแถวส่วนหัวที่ควรทำซ้ำในหน้าถัดไป

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
ในที่สุดสหรัฐฯ

  จำเป็นต้องบันทึกเอกสารที่แก้ไขโดยมีแถวส่วนหัวซ้ำกันในหน้าถัดไปของตาราง ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการทำซ้ำแถวบนเพจถัดไปโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำซ้ำแถวของตารางในหน้าถัดไปของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้โค้ด C# ที่ให้มา คุณสามารถระบุบรรทัดที่จะทำซ้ำตามความต้องการเฉพาะของคุณในเอกสาร Word ของคุณได้