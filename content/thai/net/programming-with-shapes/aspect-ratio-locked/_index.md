---
title: อัตราส่วนภาพถูกล็อค
linktitle: อัตราส่วนภาพถูกล็อค
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีล็อคหรือปลดล็อคอัตราส่วนภาพของรูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/aspect-ratio-locked/
---

บทช่วยสอนนี้จะอธิบายวิธีการล็อคหรือปลดล็อคอัตราส่วนภาพของรูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการล็อคอัตราส่วนภาพ คุณสามารถรักษาสัดส่วนเดิมของรูปร่างได้เมื่อทำการปรับขนาด

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
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกรูปร่างรูปภาพ
 ใช้`InsertImage` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกรูปร่างรูปภาพลงในเอกสาร ระบุเส้นทางไปยังไฟล์รูปภาพเป็นพารามิเตอร์

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## ขั้นตอนที่ 4: ล็อคหรือปลดล็อคอัตราส่วนภาพ
 ตั้ง`AspectRatioLocked` คุณสมบัติของรูปร่างไป`true` หรือ`false` เพื่อล็อคหรือปลดล็อคอัตราส่วนภาพตามลำดับ

```csharp
shape.AspectRatioLocked = false; //ปลดล็อคอัตราส่วนภาพ
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.AspectRatioLocked.docx"

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับอัตราส่วนภาพที่ถูกล็อคโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

แค่นั้นแหละ! คุณได้ล็อกหรือปลดล็อกอัตราส่วนกว้างยาวของรูปร่างในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET