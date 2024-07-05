---
title: เพิ่มมุมที่สนิป
linktitle: เพิ่มมุมที่สนิป
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มรูปร่างที่มีมุมที่ตัดทอนลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/add-corners-snipped/
---

 บทช่วยสอนนี้จะอธิบายวิธีเพิ่มรูปร่างที่มีมุมที่ตัดทอนลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET รูปร่างที่ตัดมุมสามารถปรับแต่งและแทรกได้โดยใช้`InsertShape` วิธี.

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

## ขั้นตอนที่ 3: แทรกรูปร่างที่ตัดมุม
 ใช้`InsertShape` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกรูปร่างโดยหักมุม ระบุประเภทรูปร่าง (ในกรณีนี้`ShapeType.TopCornersSnipped`) และระบุขนาดรูปร่างที่ต้องการ

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.AddCornersSnipped.docx"

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Add Corners Snipped โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

แค่นั้นแหละ! คุณได้เพิ่มรูปร่างที่ตัดมุมลงในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET