---
title: ตั้งค่าการจัดรูปแบบแถวของตาราง
linktitle: ตั้งค่าการจัดรูปแบบแถวของตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าการจัดรูปแบบแถวตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อตั้งค่าการจัดรูปแบบแถวตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีปรับความสูงและช่องว่างภายในของแถวตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

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
Table table = builder. StartTable();
builder. InsertCell();
```

## ขั้นตอนที่ 4: กำหนดการจัดรูปแบบเส้น
 ตอนนี้เราสามารถตั้งค่าการจัดรูปแบบแถวได้โดยเข้าไปที่`RowFormat` วัตถุของ`DocumentBuilder` วัตถุ. เราสามารถตั้งค่าความสูงของเส้นและระยะขอบ (ช่องว่างภายใน) โดยใช้คุณสมบัติที่เกี่ยวข้อง

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ขั้นตอนที่ 5: ตั้งค่าระยะขอบของตาราง
 ต่อไปเราสามารถตั้งค่าช่องว่างภายในตารางได้โดยการเข้าถึงคุณสมบัติที่เกี่ยวข้องของ`Table` วัตถุ. ระยะขอบเหล่านี้จะใช้กับทุกแถวของตาราง

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ขั้นตอนที่ 6: เพิ่มเนื้อหาลงในแถว
 สุดท้ายนี้ เราสามารถเพิ่มเนื้อหาลงในบรรทัดโดยใช้ตัวสร้างเอกสารได้`Writeln()` วิธี.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ขั้นตอนที่ 7: เสร็จสิ้นตารางและบันทึกเอกสาร
ใน

 ท้ายที่สุด เราสร้างตารางให้เสร็จสิ้นโดยใช้`EndRow()` และ`EndTable()` จากนั้นเราจะบันทึกเอกสารที่แก้ไขลงในไฟล์

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าการจัดรูปแบบแถวตารางโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// คุณสมบัติการจัดรูปแบบเหล่านี้ตั้งค่าไว้บนตารางและนำไปใช้กับแถวทั้งหมดในตาราง
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าการจัดรูปแบบแถวของตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถปรับความสูงและระยะขอบของแถวตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งเค้าโครงภาพของตารางได้ตามความต้องการเฉพาะของคุณ