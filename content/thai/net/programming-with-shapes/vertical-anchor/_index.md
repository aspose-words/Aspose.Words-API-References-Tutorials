---
title: สมอแนวตั้ง
linktitle: สมอแนวตั้ง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีวางตำแหน่งรูปร่างในแนวตั้งภายในเอกสารโดยใช้ฟีเจอร์จุดยึดแนวตั้งใน Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/vertical-anchor/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ฟีเจอร์จุดยึดแนวตั้งใน Aspose.Words สำหรับ .NET เพื่อวางตำแหน่งรูปร่างในแนวตั้งภายในเอกสาร ด้วยการตั้งค่าคุณสมบัติจุดยึดแนวตั้งของรูปร่าง คุณสามารถควบคุมการจัดตำแหน่งตามแนวตั้งโดยสัมพันธ์กับข้อความหรือหน้าได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และ DocumentBuilder
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder`คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกและกำหนดค่ารูปร่าง
 แทรกรูปร่างลงในเอกสารโดยใช้`InsertShape` วิธีการของ`DocumentBuilder` วัตถุ. กำหนดขนาดรูปร่างที่ต้องการ

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## ขั้นตอนที่ 4: ตั้งค่าจุดยึดแนวตั้ง
ตั้งค่าคุณสมบัติจุดยึดแนวตั้งของรูปร่างเพื่อควบคุมการจัดตำแหน่งตามแนวตั้ง ในตัวอย่างนี้ เราตั้งค่าเป็น "ด้านล่าง" เพื่อยึดรูปร่างไว้ที่ด้านล่างของข้อความหรือหน้า

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## ขั้นตอนที่ 5: เพิ่มเนื้อหาลงในรูปร่าง
 ใช้`MoveTo` วิธีการของ`DocumentBuilder` วัตถุเพื่อเลื่อนเคอร์เซอร์ไปที่ย่อหน้าแรกของรูปร่าง จากนั้นใช้`Write` วิธีการเพิ่มเนื้อหาให้กับรูปร่าง

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.VerticalAnchor.docx"

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Vertical Anchor โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

แค่นั้นแหละ! คุณใช้ฟีเจอร์จุดยึดแนวตั้งใน Aspose.Words สำหรับ .NET เพื่อวางตำแหน่งรูปร่างในแนวตั้งภายในเอกสารได้สำเร็จ