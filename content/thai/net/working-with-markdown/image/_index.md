---
title: ภาพ
linktitle: ภาพ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกและปรับแต่งรูปภาพด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/image/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้ฟีเจอร์รูปภาพกับ Aspose.Words สำหรับ .NET รูปภาพช่วยให้คุณสามารถแทรกภาพประกอบและกราฟิกลงในเอกสารได้

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การแทรกรูปภาพ

 เราสามารถแทรกรูปภาพโดยใช้`Shape` class และระบุประเภทของรูปภาพได้ที่นี่`ShapeType.Image` - เรายังตั้งค่าประเภทการตัดคำของรูปภาพด้วย`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## ขั้นตอนที่ 3: การปรับแต่งรูปภาพ

 เราปรับแต่งรูปภาพโดยระบุเส้นทางแบบเต็ม เป็นต้น`"/attachment/1456/pic001.png"`และเพิ่มชื่อให้กับรูปภาพ

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### ตัวอย่างซอร์สโค้ดสำหรับรูปภาพด้วย Aspose.Words สำหรับ .NET

```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

// ใส่รูปภาพ.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้คุณสมบัติรูปภาพกับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: ฉันจะแทรกรูปภาพจากไฟล์ในเครื่องลงใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการแทรกรูปภาพจากไฟล์ในเครื่องลงใน Aspose.Words คุณสามารถใช้ไฟล์`Shape` ชั้นเรียนและ`InsertImage` วิธี.

#### ถาม: ฉันสามารถแทรกรูปภาพจาก URL ใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถแทรกรูปภาพจาก URL ใน Aspose.Words ได้ คุณสามารถใช้เหมือนกัน`InsertImage`และระบุ URL รูปภาพแทนเส้นทางไฟล์ในเครื่อง

#### ถาม: ฉันจะปรับขนาดรูปภาพใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการปรับขนาดรูปภาพใน Aspose.Words คุณสามารถใช้`Width` และ`Height` คุณสมบัติของ`Shape` วัตถุ วัตถุ

#### ถาม: ฉันสามารถใช้ฟิลเตอร์กับรูปภาพใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้ฟิลเตอร์กับรูปภาพใน Aspose.Words ได้ ตัวอย่างเช่น คุณสามารถใช้ฟิลเตอร์เบลอกับรูปภาพได้โดยใช้`ApplyGaussianBlur` วิธีการของ`Shape` วัตถุ วัตถุ

#### ถาม: ฉันจะแทนที่รูปภาพหนึ่งด้วยรูปภาพอื่นใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการแทนที่รูปภาพหนึ่งด้วยรูปภาพอื่นใน Aspose.Words คุณสามารถใช้`Replace` วิธีการของ`Shape` ชั้นเรียน วิธีการนี้ใช้เป็นพารามิเตอร์`Shape` วัตถุของภาพที่จะถูกแทนที่และ`Shape` วัตถุของภาพใหม่