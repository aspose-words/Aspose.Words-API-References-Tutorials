---
title: ปรับให้พอดีกับความกว้างของหน้าอัตโนมัติ
linktitle: ปรับให้พอดีกับความกว้างของหน้าอัตโนมัติ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปรับตารางให้พอดีกับความกว้างของหน้าในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/auto-fit-to-page-width/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อปรับตารางให้พอดีกับความกว้างของหน้าในเอกสาร Word โดยอัตโนมัติ เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถจัดการตารางในเอกสาร Word โดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างและกำหนดค่าเอกสาร
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องสร้างเอกสารและกำหนดค่าตัวสร้างเอกสาร ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและตัวสร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การแทรกและการกำหนดค่าตาราง
ต่อไป เราจะแทรกตารางลงในเอกสารโดยมีความกว้างซึ่งใช้ความกว้างครึ่งหนึ่งของหน้า ใช้รหัสต่อไปนี้:

```csharp
// แทรกตารางและกำหนดค่าความกว้าง
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

ที่นี่เราใช้ตัวสร้างเอกสารเพื่อเริ่มสร้างตาราง แทรกเซลล์ และตั้งค่าความกว้างของตารางที่ต้องการเป็น 50% ของความกว้างหน้า จากนั้นเราจะเพิ่มข้อความในแต่ละเซลล์

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้ายนี้ เราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยปรับตารางตามความกว้างของหน้า ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอกสารที่แก้ไข
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต
  
### ตัวอย่างซอร์สโค้ดสำหรับปรับให้พอดีกับความกว้างของหน้าอัตโนมัติโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// แทรกตารางที่มีความกว้างซึ่งใช้ความกว้างครึ่งหนึ่งของหน้า
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับตารางให้พอดีกับความกว้างของหน้าโดยอัตโนมัติในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และการใช้โค้ด C# ที่ให้มา คุณสามารถจัดการตารางในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสามารถปรับความกว้างของตารางแบบไดนามิกตามหน้าได้ จึงทำให้เอกสารมีความเป็นมืออาชีพและดึงดูดสายตา