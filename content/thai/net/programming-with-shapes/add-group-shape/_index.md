---
title: เพิ่มรูปร่างกลุ่ม
linktitle: เพิ่มรูปร่างกลุ่ม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มรูปร่างกลุ่มที่มีหลายรูปร่างลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/add-group-shape/
---

บทช่วยสอนนี้จะอธิบายวิธีเพิ่มรูปร่างกลุ่มที่มีรูปร่างหลายแบบลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET รูปร่างกลุ่มทำให้คุณสามารถรวมและจัดการรูปร่างหลายรูปให้เป็นเอนทิตีเดียวได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และ GroupShape
 สร้างอินสแตนซ์ใหม่ของ`Document` ชั้นเรียนและ`GroupShape` คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## ขั้นตอนที่ 3: สร้างและเพิ่มรูปร่างให้กับ GroupShape
 สร้างรูปร่างเฉพาะบุคคลเช่น`accentBorderShape` และ`actionButtonShape` ใช้`Shape` ระดับ. ปรับแต่งคุณสมบัติตามต้องการ ผนวกรูปร่างเหล่านี้เข้ากับ`groupShape` วัตถุ.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## ขั้นตอนที่ 4: กำหนดขนาดสำหรับ GroupShape
 กำหนดความกว้าง ความสูง และขนาดพิกัดสำหรับ`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## ขั้นตอนที่ 5: แทรก GroupShape ลงในเอกสาร
 สร้างก`DocumentBuilder` วัตถุและแทรก`groupShape` ลงในเอกสารโดยใช้`InsertNode` วิธี.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.AddGroupShape.docx"

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มรูปร่างกลุ่มโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

แค่นั้นแหละ! คุณได้เพิ่มรูปร่างกลุ่มที่มีรูปร่างหลายแบบลงในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.W