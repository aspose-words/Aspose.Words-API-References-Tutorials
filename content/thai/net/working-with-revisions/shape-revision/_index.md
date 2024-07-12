---
title: การแก้ไขรูปร่าง
linktitle: การแก้ไขรูปร่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: แก้ไขรูปร่างในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/shape-revision/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะอธิบายวิธีการแก้ไขรูปร่างในเอกสาร Word โดยใช้ Aspose.Words for .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: การสร้างเอกสารและเพิ่มรูปร่าง

ขั้นตอนแรกคือการสร้างเอกสารใหม่และเพิ่มรูปร่าง

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## ขั้นตอนที่ 2: ติดตามการแก้ไขและเพิ่มรูปร่างอื่น

เราจะเปิดการติดตามการแก้ไขและเพิ่มรูปร่างอื่น

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## ขั้นตอนที่ 3: รับคอลเลกชันรูปร่างและตรวจสอบการแก้ไข

เราจะรวบรวมรูปร่างจากเอกสารและตรวจสอบการแก้ไขที่เกี่ยวข้องกับรูปร่างแต่ละรูป

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## ขั้นตอนที่ 4: ตรวจสอบการแก้ไขการย้ายรูปร่าง

เราจะโหลดเอกสารที่มีอยู่ซึ่งมีการแก้ไขการแทนที่รูปร่าง และตรวจสอบการแก้ไขที่เกี่ยวข้อง

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแก้ไขรูปร่างโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแก้ไขรูปร่างในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document();

//แทรกรูปร่างอินไลน์โดยไม่ต้องติดตามการแก้ไข
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// เริ่มติดตามการแก้ไขแล้วแทรกรูปร่างอื่น
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// รับคอลเลกชันรูปร่างของเอกสารซึ่งมีเพียงสองรูปร่างที่เราเพิ่มเข้าไป
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// ลบรูปร่างแรก
shapes[0].Remove();

// เนื่องจากเราได้ลบรูปร่างนั้นออกในขณะที่กำลังติดตามการเปลี่ยนแปลง รูปร่างจึงนับเป็นการแก้ไขแบบลบ
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// และเราได้แทรกรูปร่างอื่นในขณะที่ติดตามการเปลี่ยนแปลง ดังนั้นรูปร่างนั้นจะนับเป็นการแก้ไขการแทรก
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// เอกสารมีรูปร่างเดียวที่ถูกย้าย แต่การแก้ไขการย้ายรูปร่างจะมีรูปร่างนั้นสองอินสแตนซ์
// อันหนึ่งจะเป็นรูปร่าง ณ จุดหมายปลายทางที่มาถึง และอีกอันจะเป็นรูปร่าง ณ ตำแหน่งเดิม
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// นี่คือการย้ายไปสู่การแก้ไข รวมถึงรูปร่างของจุดหมายปลายทางที่มาถึงด้วย
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// นี่คือการย้ายจากการแก้ไขซึ่งเป็นรูปร่างที่ตำแหน่งเดิม
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแก้ไขรูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนในการสร้างเอกสาร เปิดใช้งานการติดตามการแก้ไข ตรวจสอบการแก้ไขที่เกี่ยวข้องกับรูปร่างแต่ละรูปร่าง และตรวจสอบการแก้ไขเพื่อย้ายรูปร่าง เราก็สามารถจัดการการแก้ไขได้สำเร็จ Aspose.Words สำหรับ .NET นำเสนอ API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมบทวิจารณ์และแบบฟอร์มในเอกสาร Word

### คำถามที่พบบ่อย

#### ถาม: ฉันจะสร้างเอกสารใหม่และเพิ่มรูปร่างใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการสร้างเอกสารใหม่และเพิ่มรูปร่างใน Aspose.Words สำหรับ .NET คุณสามารถใช้โค้ดต่อไปนี้ ที่นี่เราเพิ่มสองรูปร่าง ลูกบาศก์และดวงอาทิตย์ ในส่วนแรกของเอกสาร:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### ถาม: ฉันจะเปิดใช้งานการติดตามการแก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปิดใช้งานการติดตามการแก้ไขใน Aspose.Words สำหรับ .NET คุณสามารถใช้`StartTrackRevisions` วิธีการของ`Document` วัตถุ. วิธีการนี้ใช้ชื่อผู้เขียนการแก้ไขเป็นพารามิเตอร์:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### ถาม: ฉันจะตรวจสอบการแก้ไขที่เกี่ยวข้องกับแต่ละรูปร่างในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการตรวจสอบการแก้ไขที่เกี่ยวข้องกับแต่ละรูปร่างในเอกสาร Aspose.Words สำหรับ .NET คุณสามารถรับคอลเลกชันรูปร่างของเอกสารได้โดยใช้`GetChildNodes` วิธีการด้วย`NodeType.Shape` ประเภทโหนด จากนั้นคุณก็จะสามารถเข้าถึงรูปร่างแต่ละแบบได้`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , และ`IsMoveToRevision` คุณสมบัติเพื่อกำหนดประเภทของการแก้ไขที่เกี่ยวข้องกับรูปร่าง:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### ถาม: ฉันจะตรวจสอบการแก้ไขการกระจัดของรูปร่างในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการตรวจสอบการแก้ไขการแทนที่รูปร่างในเอกสาร Aspose.Words สำหรับ .NET คุณสามารถโหลดเอกสารที่มีอยู่ซึ่งมีการแก้ไขการแทนที่รูปร่างได้ จากนั้นคุณก็จะสามารถเข้าถึงรูปร่างแต่ละแบบได้`IsMoveFromRevision`และ`IsMoveToRevision` คุณสมบัติเพื่อตรวจสอบว่ามีการเคลื่อนย้ายหรือไม่ และหากเป็นเช่นนั้น จากที่ไหน และไปที่ใด:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```