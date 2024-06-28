---
title: ผสานแนวตั้ง
linktitle: ผสานแนวตั้ง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผสานเซลล์ในแนวตั้งในตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/vertical-merge/
---

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีผสานเซลล์ในแนวตั้งในตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถผสานเซลล์ในแนวตั้งในตารางของคุณในเอกสาร Word ได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำกับเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารใหม่
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การรวมเซลล์แนวตั้ง
ต่อไปเราจะรวมเซลล์แนวตั้งในตาราง ใช้รหัสต่อไปนี้:

```csharp
// แทรกเซลล์
builder. InsertCell();

// ใช้การผสานแนวตั้งกับเซลล์แรก
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// แทรกเซลล์อื่น
builder. InsertCell();

// ไม่ใช้การผสานแนวตั้งกับเซลล์
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// แทรกเซลล์
builder. InsertCell();

// ใช้การผสานแนวตั้งกับเซลล์ก่อนหน้า
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// แทรกเซลล์อื่น
builder. InsertCell();

// ไม่ใช้การผสานแนวตั้งกับเซลล์
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//สิ้นสุดการสร้างตาราง
builder. EndTable();
```

ในโค้ดนี้ เราใช้ตัวสร้าง DocumentBuilder เพื่อแทรกเซลล์ลงในตาราง เราใช้การผสานแนวตั้งกับเซลล์โดยใช้คุณสมบัติ CellFormat.VerticalMerge เราใช้ CellMerge.First สำหรับการผสานเซลล์ครั้งแรก CellMerge.Previous เพื่อผสานกับเซลล์ก่อนหน้า และใช้ CellMerge.None สำหรับการไม่มีการผสานในแนวตั้ง

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่แก้ไขด้วยเซลล์ที่ผสาน ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการผสานแนวตั้งโดยใช้ Aspose.Words สำหรับ .NET 
```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// เซลล์นี้ผสานในแนวตั้งกับเซลล์ด้านบน และควรว่างเปล่า
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีผสานเซลล์ในแนวตั้งในตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะสามารถผสานเซลล์แนวตั้งในตารางของคุณได้อย่างง่ายดาย