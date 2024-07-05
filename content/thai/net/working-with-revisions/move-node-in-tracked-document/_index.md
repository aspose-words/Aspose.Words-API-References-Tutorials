---
title: ย้ายโหนดในเอกสารที่ติดตาม
linktitle: ย้ายโหนดในเอกสารที่ติดตาม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ย้ายโหนดในเอกสารที่ติดตามด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/move-node-in-tracked-document/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะอธิบายวิธีย้ายโหนดในเอกสาร Word ที่ติดตามโดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: การสร้างเอกสาร

ขั้นตอนแรกคือการสร้างเอกสารใหม่และเพิ่มย่อหน้า

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## ขั้นตอนที่ 2: ติดตามการแก้ไข

เราจะเปิดใช้งานการติดตามการแก้ไขในเอกสาร

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## ขั้นตอนที่ 3: ย้ายโหนด

เราจะย้ายโหนด (ย่อหน้า) จากตำแหน่งหนึ่งไปยังอีกตำแหน่งหนึ่งในขณะที่สร้างการแก้ไข

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## ขั้นตอนที่ 4: หยุดการติดตามบทวิจารณ์

เราจะหยุดติดตามการแก้ไขในเอกสาร

```csharp
doc.StopTrackRevisions();
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save`วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### ตัวอย่างซอร์สโค้ดสำหรับโหนดย้ายในเอกสารที่ถูกติดตามโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับการย้ายโหนดในเอกสารที่ถูกติดตามโดยใช้ Aspose.Words สำหรับ .NET:


```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// เริ่มติดตามการแก้ไข
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// สร้างการแก้ไขเมื่อย้ายโหนดจากที่หนึ่งไปยังอีกที่หนึ่ง
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// หยุดกระบวนการติดตามการแก้ไข
doc.StopTrackRevisions();

// มีอีก 3 ย่อหน้าในช่วงการย้ายจาก
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีย้ายโหนดในเอกสาร Word ที่ติดตามโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนในการสร้างเอกสาร การเปิดใช้งานการติดตามการแก้ไข การย้ายโหนด และการหยุดการติดตามการแก้ไข เราจึงสามารถดำเนินการจัดการนี้ได้สำเร็จ Aspose.Words for .NET เป็นเครื่องมืออันทรงพลังสำหรับการประมวลผลคำด้วยเอกสาร Word และนำเสนอคุณสมบัติขั้นสูงสำหรับการจัดการการแก้ไข ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อย้ายโหนดในเอกสาร Word ของคุณเองในขณะที่ติดตามการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเปิดใช้งานการติดตามการแก้ไขในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปิดใช้งานการติดตามการแก้ไขในเอกสาร Aspose.Words สำหรับ .NET คุณสามารถใช้`StartTrackRevisions` วิธีการของ`Document` วัตถุ. วิธีการนี้ใช้พารามิเตอร์ชื่อผู้เขียนการแก้ไขและวันที่เริ่มต้นการติดตามผลการแก้ไข

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### ถาม: ฉันจะย้ายโหนดในเอกสารที่ถูกติดตามโดยไม่สร้างการแก้ไขได้อย่างไร

 ตอบ: หากคุณต้องการย้ายโหนดในเอกสารที่ติดตามโดยไม่สร้างการแก้ไข คุณสามารถใช้`Remove` และ`InsertAfter` หรือ`InsertBefore` วิธีการของ`Node` วัตถุ. ตัวอย่างเช่น เมื่อต้องการย้ายย่อหน้าหลังจากย่อหน้าอื่น คุณสามารถใช้โค้ดต่อไปนี้:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### ถาม: ฉันจะหยุดการติดตามการแก้ไขในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการหยุดติดตามการแก้ไขในเอกสาร Aspose.Words สำหรับ .NET คุณสามารถใช้`StopTrackRevisions` วิธีการของ`Document` วัตถุ.

```csharp
doc.StopTrackRevisions();
```