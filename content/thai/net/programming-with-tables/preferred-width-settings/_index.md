---
title: การตั้งค่าความกว้างที่ต้องการ
linktitle: การตั้งค่าความกว้างที่ต้องการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าความกว้างของเซลล์ตารางที่ต้องการในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/preferred-width-settings/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีตั้งค่าความกว้างที่ต้องการสำหรับเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถระบุความกว้างที่ต้องการสำหรับเซลล์ตารางในเอกสาร Word ได้

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

## ขั้นตอนที่ 3: สร้างตารางที่มีความกว้างที่ต้องการ
ต่อไป เราจะสร้างตารางที่มีเซลล์ 3 เซลล์ซึ่งมีความกว้างที่ต้องการต่างกัน ใช้รหัสต่อไปนี้:

```csharp
// จุดเริ่มต้นของตาราง
builder. StartTable();

// แทรกเซลล์ที่มีขนาดสัมบูรณ์
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// แทรกเซลล์ที่มีขนาดสัมพันธ์กัน (เป็นเปอร์เซ็นต์)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// แทรกเซลล์ที่ปรับขนาดอัตโนมัติ
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// ท้ายตาราง
builder. EndTable();
```

ที่นี่เราใช้ตัวสร้างเอกสารเพื่อสร้างตารางที่มีสามเซลล์ เซลล์แรกมีความกว้างที่ต้องการ 40 พอยต์ เซลล์ที่สองมีความกว้างที่ต้องการ 20% ของความกว้างของตาราง และเซลล์ที่สามมีความกว้างที่ต้องการโดยอัตโนมัติที่ปรับ

  ขึ้นอยู่กับพื้นที่ว่าง

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่แก้ไขด้วยการตั้งค่าความกว้างที่ต้องการซึ่งกำหนดไว้สำหรับเซลล์ตาราง ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งค่าความกว้างที่ต้องการโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// แทรกแถวของตารางที่ประกอบด้วยสามเซลล์ซึ่งมีความกว้างที่ต้องการต่างกัน
	builder.StartTable();
	// แทรกเซลล์ที่มีขนาดสมบูรณ์
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// แทรกเซลล์ที่มีขนาดสัมพันธ์ (เปอร์เซ็นต์)
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// แทรกเซลล์ขนาดอัตโนมัติ
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าความกว้างที่ต้องการสำหรับเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะสามารถปรับแต่งความกว้างของเซลล์ตารางให้ตรงตามความต้องการเฉพาะของคุณในเอกสาร Word ได้