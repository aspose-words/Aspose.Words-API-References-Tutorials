---
title: ใช้การจัดรูปแบบแถว
linktitle: ใช้การจัดรูปแบบแถว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่อใช้การจัดรูปแบบแถวกับตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อใช้การจัดรูปแบบแถวกับตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการจัดรูปแบบแถวของตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 3: เริ่มบอร์ดใหม่
 หากต้องการใช้การจัดรูปแบบแถว เราต้องเริ่มตารางใหม่โดยใช้`StartTable()` วิธีการของตัวสร้างเอกสาร

```csharp
Table table = builder. StartTable();
```

## ขั้นตอนที่ 4: แทรกเซลล์และไปที่รูปแบบแถว
ตอนนี้เราสามารถแทรกเซลล์ลงในตารางและเข้าถึงรูปแบบแถวของเซลล์นั้นได้โดยใช้ตัวสร้างเอกสาร`InsertCell()`และ`RowFormat` วิธีการ

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## ขั้นตอนที่ 5: ตั้งค่าความสูงของแถว
 ในการกำหนดความสูงของแถว เราใช้`Height`และ`HeightRule` คุณสมบัติของรูปแบบแถว ในตัวอย่างนี้ เราตั้งค่าความสูงของแถวเป็น 100 จุด และใช้`Exactly` กฎ.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ขั้นตอนที่ 6: กำหนดการจัดรูปแบบตาราง
 คุณสมบัติการจัดรูปแบบบางอย่างสามารถตั้งค่าบนตารางได้ และนำไปใช้กับแถวตารางทั้งหมด ในตัวอย่างนี้ เราตั้งค่าคุณสมบัติระยะขอบของตารางโดยใช้`LeftPadding`, `RightPadding`, `TopPadding`และ`BottomPadding` คุณสมบัติ.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ขั้นตอนที่ 7: เพิ่มเนื้อหาลงในแถว
ตอนนี้เราทำได้

 เราจะเพิ่มเนื้อหาลงในบรรทัดโดยใช้วิธีการของตัวสร้างเอกสาร ในตัวอย่างนี้ เราใช้`Writeln()` วิธีการเพิ่มข้อความในบรรทัด

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ขั้นตอนที่ 8: จบเส้นและตาราง
 เมื่อเราเพิ่มเนื้อหาลงในแถวแล้ว เราก็สามารถจบแถวโดยใช้`EndRow()` วิธีการแล้วจบตารางโดยใช้`EndTable()` วิธี.

```csharp
builder. EndRow();
builder. EndTable();
```

## ขั้นตอนที่ 9: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจะบันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

ขอแสดงความยินดี! ขณะนี้คุณได้ใช้การจัดรูปแบบแถวกับตารางโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับใช้การจัดรูปแบบแถวโดยใช้ Aspose.Words สำหรับ .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีนำการจัดรูปแบบแถวไปใช้กับตารางโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถรวมฟังก์ชันนี้เข้ากับโปรเจ็กต์ C# ของคุณได้อย่างง่ายดาย การจัดการการจัดรูปแบบแถวตารางเป็นส่วนสำคัญของการประมวลผลเอกสาร และ Aspose.Words ก็มี API ที่ทรงพลังและยืดหยุ่นเพื่อให้บรรลุเป้าหมายนี้ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและปฏิบัติตามข้อกำหนดเฉพาะได้