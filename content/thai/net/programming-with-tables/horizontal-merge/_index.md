---
title: การผสานแนวนอน
linktitle: การผสานแนวนอน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผสานเซลล์ในตาราง Word ในแนวนอนด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/horizontal-merge/
---

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีผสานเซลล์ในตารางในเอกสาร Word ในแนวนอนโดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถผสานเซลล์ในแนวนอนในตาราง Word ของคุณโดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและการเริ่มต้นตัวสร้างเอกสาร
ในการเริ่มการประมวลผลคำด้วยตารางและเซลล์ เราจำเป็นต้องสร้างเอกสารใหม่และเริ่มต้นตัวสร้างเอกสาร ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//สร้างเอกสารและเริ่มต้นตัวสร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: สร้างตารางด้วยการรวมเซลล์ในแนวนอน
ต่อไป เราจะสร้างตารางและใช้การรวมเซลล์แนวนอนโดยใช้คุณสมบัติที่ได้รับจาก Aspose.Words สำหรับ .NET ใช้รหัสต่อไปนี้:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// เซลล์นี้ถูกผสานกับเซลล์ก่อนหน้า และควรว่างเปล่า
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 ที่นี่เราใช้ตัวสร้างเอกสารเพื่อสร้างตารางและตั้งค่าคุณสมบัติการรวมเซลล์ในแนวนอน เราใช้`HorizontalMerge` ทรัพย์สินของ`CellFormat` วัตถุเพื่อระบุประเภทของการผสานแนวนอนที่จะใช้กับแต่ละเซลล์ โดยใช้`CellMerge.First` เรารวมเซลล์แรกเข้ากับเซลล์ถัดไปขณะใช้งาน`CellMerge.Previous` เรารวมเซลล์ปัจจุบันกับเซลล์ก่อนหน้า`CellMerge.None` บ่งชี้ว่าไม่ควรรวมเซลล์

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยให้เซลล์ผสานกันในแนวนอน ใช้รหัสต่อไปนี้:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการผสานแนวนอนโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// เซลล์นี้ถูกผสานเข้ากับเซลล์ก่อนหน้า และควรว่างเปล่า
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีผสานเซลล์ในตารางในเอกสาร Word ในแนวนอนโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะสามารถใช้การรวมเซลล์แนวนอนในตาราง Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสร้างเค้าโครงตารางที่ซับซ้อนมากขึ้นและจัดระเบียบข้อมูลของคุณได้ดีขึ้น