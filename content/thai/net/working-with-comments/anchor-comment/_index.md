---
title: ความคิดเห็นของสมอ
linktitle: ความคิดเห็นของสมอ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธียึดคำตอบความคิดเห็นกับข้อความเฉพาะในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-comments/anchor-comment/
---

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธียึดคำตอบความคิดเห็นกับข้อความเฉพาะในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถเชื่อมโยงความคิดเห็นกับข้อความเฉพาะในเอกสารของคุณได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และเพิ่มข้อความ
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document และเพิ่มข้อความที่ต้องการ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## ขั้นตอนที่ 2: สร้างความคิดเห็นและเพิ่มช่วงความคิดเห็น
จากนั้น สร้างความคิดเห็นและเชื่อมโยงกับข้อความเฉพาะโดยใช้อ็อบเจ็กต์ CommentRangeStart และ CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
หลังจากยึดความคิดเห็นไว้ที่ข้อความเฉพาะแล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับการตอบกลับความคิดเห็น Anchor โดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการยึดคำตอบความคิดเห็นโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
// สร้างอินสแตนซ์ของเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// สร้างวัตถุ Run สามรายการ
//สองรายการแรกเรียกใช้ข้อความ ในขณะที่รายการที่สามเรียกใช้ความคิดเห็น

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// แต่ละวัตถุ Run มีวัตถุ CommentRangeStart และ CommentRangeEnd ที่เกี่ยวข้องกัน

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### คำถามที่พบบ่อย

#### ถาม: Anchor ความคิดเห็นใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: ใน Aspose.Words สำหรับ .NET จุดยึดความคิดเห็นคือเครื่องหมายที่เชื่อมต่อความคิดเห็นไปยังตำแหน่งเฉพาะในเอกสาร

#### ถาม: ฉันจะเพิ่มจุดยึดความคิดเห็นในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเพิ่มจุดยึดความคิดเห็นในเอกสาร Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนที่กล่าวถึงในบทช่วยสอน

#### ถาม: ฉันจะเข้าถึงจุดยึดความคิดเห็นที่มีอยู่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถเข้าถึงจุดยึดความคิดเห็นที่มีอยู่ใน Aspose.Words สำหรับ .NET ได้โดยใช้`Comment.Anchor` คุณสมบัติ.

#### ถาม: ฉันสามารถสนับสนุนจุดยึดความคิดเห็นใน Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถลบจุดยึดความคิดเห็นใน Aspose.Words สำหรับ .NET ได้โดยใช้`Comment.Remove` วิธี.

#### ถาม: ฉันจะแก้ไขข้อความของความคิดเห็นที่เชื่อมโยงกับจุดยึดความคิดเห็นใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการแก้ไขข้อความของความคิดเห็นที่เชื่อมโยงกับจุดยึดความคิดเห็นใน Aspose.Words สำหรับ .NET คุณสามารถเข้าถึง`Comment.Text` ทรัพย์สินที่เกี่ยวข้อง`Comment` วัตถุและแก้ไขข้อความตามต้องการ

