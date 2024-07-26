---
title: รับคะแนนขอบเขตรูปร่างจริง
linktitle: รับคะแนนขอบเขตรูปร่างจริง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงขอบเขตที่แท้จริงของรูปร่างเป็นจุด (หน่วยการวัด) ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/get-actual-shape-bounds-points/
---

บทช่วยสอนนี้จะอธิบายวิธีการดึงขอบเขตที่แท้จริงของรูปร่างเป็นจุด (หน่วยการวัด) ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ขอบเขตแสดงถึงขนาดและตำแหน่งของรูปร่างภายในเอกสาร

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกรูปร่างรูปภาพ
 ใช้`InsertImage` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกรูปร่างรูปภาพลงในเอกสาร ระบุเส้นทางไปยังไฟล์รูปภาพเป็นพารามิเตอร์

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## ขั้นตอนที่ 3: รับคะแนนขอบเขตรูปร่างจริง
 เข้าถึงรูปร่างของ`ShapeRenderer` ใช้`GetShapeRenderer` วิธี. จากนั้นดึงขอบเขตที่แท้จริงของรูปร่างเป็นจุดโดยใช้`BoundsInPoints` คุณสมบัติ.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### ตัวอย่างซอร์สโค้ดสำหรับรับคะแนนขอบเขตรูปร่างจริงโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

แค่นั้นแหละ! คุณได้ดึงขอบเขตที่แท้จริงของรูปร่างเป็นจุดในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET