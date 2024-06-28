---
title: ตั้งค่าการจัดรูปแบบเซลล์ตาราง
linktitle: ตั้งค่าการจัดรูปแบบเซลล์ตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อกำหนดการจัดรูปแบบของเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีปรับความกว้างและระยะขอบ (ช่องว่างภายใน) ของเซลล์ในตารางของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

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
ในการเริ่มสร้างตาราง เราใช้`StartTable()` วิธีการของตัวสร้างเอกสาร จากนั้นเราจะเพิ่มเซลล์ลงในตารางโดยใช้`InsertCell()` วิธี.

```csharp
builder. StartTable();
builder. InsertCell();
```

## ขั้นตอนที่ 4: ตั้งค่าการจัดรูปแบบเซลล์
 ตอนนี้เราสามารถตั้งค่าการจัดรูปแบบเซลล์ได้โดยเข้าไปที่`CellFormat` วัตถุของ`DocumentBuilder` วัตถุ วัตถุ เราสามารถกำหนดความกว้างของเซลล์และระยะขอบ (ช่องว่างภายใน) โดยใช้คุณสมบัติที่เกี่ยวข้อง

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## ขั้นตอนที่ 5: เพิ่มเนื้อหาลงในเซลล์
 จากนั้นเราสามารถเพิ่มเนื้อหาลงในเซลล์โดยใช้ตัวสร้างเอกสาร`Writeln()` วิธี.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## ขั้นตอนที่ 6: เสร็จสิ้นตารางและบันทึกเอกสาร
 ในที่สุด เราก็เสร็จสิ้นการสร้างตารางโดยใช้`EndRow()` วิธีการและ`EndTable()`จากนั้นเราจะบันทึกเอกสารที่แก้ไขลงในไฟล์

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถปรับความกว้างและระยะขอบของเซลล์ในตารางในเอกสาร Word ได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งเค้าโครงภาพของตารางได้ตามความต้องการเฉพาะของคุณ