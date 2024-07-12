---
title: ตารางที่ซ้อนกัน
linktitle: ตารางที่ซ้อนกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางที่ซ้อนกันในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/nested-table/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีสร้างตารางที่ซ้อนกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถสร้างตารางที่ซ้อนกันในเอกสาร Word ของคุณโดยทางโปรแกรมได้

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

## ขั้นตอนที่ 3: สร้างตารางที่ซ้อนกัน
ต่อไป เราจะสร้างตารางที่ซ้อนกันโดยการแทรกเซลล์ลงในตารางด้านนอก และสร้างตารางใหม่ภายในเซลล์แรก ใช้รหัสต่อไปนี้:

```csharp
// แทรกเซลล์แรกของตารางด้านนอก
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// แทรกเซลล์ที่สองของตารางด้านนอก
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// การสิ้นสุดของโต๊ะด้านนอก
builder. EndTable();

// ย้ายไปยังเซลล์แรกของตารางด้านนอก
builder.MoveTo(cell.FirstParagraph);

// สร้างโต๊ะด้านใน
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// ปลายโต๊ะด้านใน
builder. EndTable();
```

ที่นี่เราใช้เครื่องมือสร้างเอกสารเพื่อแทรกเซลล์และเนื้อหาลงในตารางด้านนอก จากนั้นเราย้ายเคอร์เซอร์ตัวสร้างเอกสารไปที่เซลล์แรกของตารางด้านนอก และสร้างตารางใหม่ภายในโดยการแทรกเซลล์และเนื้อหา

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้ายนี้ เราจำเป็นต้องบันทึกเอกสารที่แก้ไขแล้วลงในตารางที่ซ้อนกัน ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

อย่าลืมระบุพาธและไฟล์ชื่อที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับ Nested Table โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// การเรียกนี้มีความสำคัญต่อการสร้างตารางที่ซ้อนกันภายในตารางแรก
	//หากไม่มีการเรียกนี้ เซลล์ที่แทรกด้านล่างจะถูกต่อท้ายตารางด้านนอก
	builder.EndTable();
	// ย้ายไปยังเซลล์แรกของตารางด้านนอก
	builder.MoveTo(cell.FirstParagraph);
	// สร้างโต๊ะด้านใน
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างตารางที่ซ้อนกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถสร้างตารางแบบซ้อนได้ตามความต้องการเฉพาะของคุณในเอกสาร Word โดยทางโปรแกรม
