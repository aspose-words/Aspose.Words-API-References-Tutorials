---
title: สร้างสไตล์ตาราง
linktitle: สร้างสไตล์ตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการสร้างสไตล์ตารางแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/create-table-style/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อสร้างสไตล์ตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีสร้างสไตล์แบบกำหนดเองสำหรับตารางของคุณในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 4: สร้างสไตล์ตาราง
 ตอนนี้เราสามารถสร้างรูปแบบตารางโดยใช้`TableStyle` ชั้นเรียนและ`Add()` วิธีการจากเอกสาร`s `คอลเลกชันสไตล์ เรากำหนดคุณสมบัติของสไตล์ เช่น เส้นขอบ ระยะขอบ และช่องว่างภายใน

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## ขั้นตอนที่ 5: ใช้สไตล์ตารางกับตาราง
 สุดท้าย เราใช้สไตล์ตารางที่เราสร้างขึ้นกับตารางโดยใช้`Style` คุณสมบัติของตาราง

```csharp
table.Style = tableStyle;
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข
สุดท้ายให้บันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

ขอแสดงความยินดี! ตอนนี้คุณได้สร้างสไตล์ที่กำหนดเองสำหรับตารางของคุณโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับสร้างสไตล์ตารางโดยใช้ Aspose.Words สำหรับ .NET 

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
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างสไตล์ตารางโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถปรับแต่งสไตล์ของตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและตอบสนองความต้องการเฉพาะได้