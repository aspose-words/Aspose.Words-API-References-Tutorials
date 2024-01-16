---
title: กำหนดการจัดรูปแบบตามเงื่อนไข
linktitle: กำหนดการจัดรูปแบบตามเงื่อนไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่อกำหนดการจัดรูปแบบตามเงื่อนไขในตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/define-conditional-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อกำหนดการจัดรูปแบบตามเงื่อนไขโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีนำการจัดรูปแบบตามเงื่อนไขไปใช้กับตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

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
ในการเริ่มสร้างตาราง เราใช้`StartTable()` วิธีการของตัวสร้างเอกสาร จากนั้นเราจะเพิ่มเซลล์ลงในตารางโดยใช้`InsertCell()` วิธีการและเราเขียนเนื้อหาของเซลล์ไปยังการใช้`Write()` วิธี.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## ขั้นตอนที่ 4: สร้างสไตล์ตารางและตั้งค่าการจัดรูปแบบตามเงื่อนไข
 ตอนนี้เราสามารถสร้างรูปแบบตารางโดยใช้`TableStyle` ชั้นเรียนและ`Add()` วิธีการจากเอกสาร`s `สไตล์` collection. We can then set the conditional formatting for the first row of the table by accessing the `รูปแบบตามเงื่อนไข` property of the table style and using the `คุณสมบัติแถวแรก

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.ConditionalStyles.FirstRow.Shading.BackgroundPatternColor = Color.GreenYellow;
tableStyle.ConditionalStyles.FirstRow.Shading.Texture = TextureIndex.TextureNone;
```

## ขั้นตอนที่ 5: ใช้สไตล์ตารางกับตาราง
 สุดท้าย เราใช้สไตล์ตารางที่เราสร้างขึ้นกับตารางโดยใช้`Style` คุณสมบัติของตาราง

```csharp
table.Style = tableStyle;
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข
สุดท้ายให้บันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและ

  ตำแหน่งที่เหมาะสมสำหรับเอกสารขาออก

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DefineConditionalFormatting.docx");
```

ขอแสดงความยินดี! ขณะนี้ คุณได้กำหนดการจัดรูปแบบตามเงื่อนไขสำหรับตารางของคุณโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับกำหนดการจัดรูปแบบตามเงื่อนไขโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.ConditionalStyles.FirstRow.Shading.BackgroundPatternColor = Color.GreenYellow;
	tableStyle.ConditionalStyles.FirstRow.Shading.Texture = TextureIndex.TextureNone;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DefineConditionalFormatting.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าการจัดรูปแบบตามเงื่อนไขโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถนำการจัดรูปแบบตามเงื่อนไขไปใช้กับตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและตอบสนองความต้องการเฉพาะได้