---
title: แทรกรูปร่าง
linktitle: แทรกรูปร่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกรูปร่างลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/insert-shape/
---

บทช่วยสอนนี้จะอธิบายวิธีแทรกรูปร่างลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET สามารถใช้รูปร่างเพื่อปรับปรุงรูปลักษณ์และเค้าโครงของเอกสารของคุณได้

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

## ขั้นตอนที่ 3: แทรกรูปร่าง
 ใช้`InsertShape` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกรูปร่างลงในเอกสาร ระบุประเภทรูปร่าง ตำแหน่งแนวนอนและแนวตั้งที่สัมพันธ์กัน ขนาดหน้า ขนาด และประเภทการตัด คุณยังสามารถกำหนดมุมการหมุนของรูปร่างได้หากต้องการ

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.InsertShape.docx"

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกรูปร่างโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

แค่นั้นแหละ! คุณได้แทรกรูปร่างลงในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words for .NET