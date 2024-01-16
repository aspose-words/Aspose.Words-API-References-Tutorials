---
title: ตรวจจับรูปร่างศิลปะอัจฉริยะ
linktitle: ตรวจจับรูปร่างศิลปะอัจฉริยะ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตรวจจับรูปร่าง Smart Art ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เพื่อระบุการแสดงภาพกราฟิก
type: docs
weight: 10
url: /th/net/programming-with-shapes/detect-smart-art-shape/
---

บทช่วยสอนนี้จะอธิบายวิธีการตรวจจับรูปร่าง Smart Art ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET รูปทรง Smart Art คือการแสดงภาพกราฟิกที่ใช้ในการนำเสนอข้อมูลและแนวคิดด้วยภาพ

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
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## ขั้นตอนที่ 3: ตรวจจับรูปร่างศิลปะอัจฉริยะ
 วนซ้ำโหนดย่อยประเภท`Shape` ในเอกสารโดยใช้`GetChildNodes`วิธี. ตรวจสอบว่าแต่ละรูปร่างมี Smart Art หรือไม่โดยใช้`HasSmart Art` คุณสมบัติ.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## ขั้นตอนที่ 4: ส่งออกผลลัพธ์
พิมพ์จำนวนรูปร่างด้วย Smart Art ที่ตรวจพบในเอกสาร

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Detect Smart Art Shape โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

แค่นั้นแหละ! คุณตรวจพบรูปร่าง Smart Art ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET