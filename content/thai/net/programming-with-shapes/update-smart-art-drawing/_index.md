---
title: อัปเดตการวาดภาพศิลปะอัจฉริยะ
linktitle: อัปเดตการวาดภาพศิลปะอัจฉริยะ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีอัปเดตภาพวาด Smart Art ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/update-smart-art-drawing/
---

บทช่วยสอนนี้จะอธิบายวิธีอัปเดตรูปวาด Smart Art ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการวนซ้ำรูปร่างต่างๆ ในเอกสารและตรวจสอบว่ารูปร่างมี Smart Art หรือไม่ คุณสามารถอัปเดตภาพวาด Smart Art เพื่อสะท้อนถึงการเปลี่ยนแปลงใดๆ ที่เกิดขึ้นกับข้อมูลได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร
 โหลดเอกสาร Word ที่มีรูปวาด Smart Art โดยใช้`Document` ตัวสร้างคลาส

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## ขั้นตอนที่ 3: อัปเดตการวาดภาพศิลปะอัจฉริยะ
 วนซ้ำรูปร่างในเอกสารโดยใช้`GetChildNodes` วิธีการด้วย`NodeType.Shape` พารามิเตอร์. ตรวจสอบว่าแต่ละรูปร่างมี Smart Art หรือไม่โดยใช้`HasSmartArt`ทรัพย์สินและหากเป็นจริงให้โทรไปที่`UpdateSmartArtDrawing` วิธีการอัพเดตภาพวาด Smart Art

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### ตัวอย่างซอร์สโค้ดสำหรับอัปเดต Smart Art Drawing โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

แค่นั้นแหละ! คุณได้อัปเดตภาพวาด Smart Art ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET