---
title: ตั้งค่าการเติมเซลล์
linktitle: ตั้งค่าการเติมเซลล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าระยะขอบของเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อตั้งค่าระยะขอบของเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีปรับระยะขอบด้านซ้าย บน ขวา และล่าง (ช่องว่าง) ของเนื้อหาเซลล์ในตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 4: ตั้งค่าระยะขอบของเซลล์
 ตอนนี้เราสามารถตั้งค่าระยะขอบของเซลล์โดยใช้`SetPaddings()` วิธีการของ`CellFormat` วัตถุ. ขอบถูกกำหนดเป็นจุดและระบุตามลำดับซ้าย บน ขวา และล่าง

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### ตัวอย่างซอร์สโค้ดสำหรับ Set Cell Padding โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// กำหนดจำนวนช่องว่าง (เป็นพอยต์) ที่จะบวกทางซ้าย/บน/ขวา/ล่างของเนื้อหาในเซลล์
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าระยะขอบของเซลล์ตารางโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถปรับระยะขอบของเซลล์เพื่อสร้างช่องว่างทางด้านซ้าย บน ขวา และล่างสุดของเนื้อหาในตารางในเอกสาร Word ได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งการจัดรูปแบบของตารางตามความต้องการเฉพาะของคุณได้