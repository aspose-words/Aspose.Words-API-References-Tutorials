---
title: เพิ่มความคิดเห็น
linktitle: เพิ่มความคิดเห็น
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มความคิดเห็นลงในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-comments/add-comments/
---

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีเพิ่มความคิดเห็นลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถแทรกความคิดเห็นและปรับแต่งเนื้อหาในเอกสารของคุณได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document และเตรียมใช้งานอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เพิ่มเนื้อหาลงในเอกสาร
จากนั้นเพิ่มเนื้อหาที่ต้องการลงในเอกสารโดยใช้วัตถุ DocumentBuilder ในตัวอย่างนี้ เราเพิ่มข้อความ:

```csharp
builder.Write("Some text is added.");
```

## ขั้นตอนที่ 3: สร้างความคิดเห็นและเพิ่มเนื้อหา
หากต้องการเพิ่มความคิดเห็น ให้สร้างอินสแตนซ์ของคลาส Comment โดยส่งอ็อบเจ็กต์ Document ชื่อผู้เขียน ชื่อย่อผู้เขียน และวันที่ปัจจุบัน:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

จากนั้น ให้เพิ่มความคิดเห็นต่อท้ายย่อหน้าปัจจุบัน:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

เพิ่มเนื้อหาลงในความคิดเห็น เช่น ย่อหน้าและข้อความ:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
หลังจากเพิ่มความคิดเห็นและเนื้อหาแล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## ตัวอย่างซอร์สโค้ดสำหรับเพิ่มความคิดเห็นโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเพิ่มความคิดเห็นโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มความคิดเห็นลงในเอกสาร Word โดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถแทรกความคิดเห็นและปรับแต่งเนื้อหาในเอกสารของคุณได้

ความคิดเห็นมีประโยชน์สำหรับการทำงานร่วมกัน การให้ข้อมูลเพิ่มเติม หรือการจดบันทึกภายในเอกสาร ทดลองใช้ชื่อผู้แต่ง ชื่อย่อ และเนื้อหาความคิดเห็นที่แตกต่างกันเพื่อให้ตรงตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเพิ่มความคิดเห็นในเอกสาร Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเพิ่มความคิดเห็นในเอกสาร Aspose.Words สำหรับ .NET คุณต้องทำตามขั้นตอนที่กล่าวถึงในบทช่วยสอน

#### ถาม: ฉันสามารถจัดรูปแบบข้อความแสดงความคิดเห็นใน Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถจัดรูปแบบข้อความแสดงความคิดเห็นใน Aspose.Words สำหรับ .NET ได้โดยใช้คุณสมบัติการจัดรูปแบบที่มีอยู่

#### ถาม: ฉันจะดึงความคิดเห็นทั้งหมดที่มีอยู่ในเอกสารได้อย่างไร

ตอบ: คุณสามารถดึงความคิดเห็นทั้งหมดที่มีอยู่ในเอกสารได้โดยใช้`Document.Comments` คุณสมบัติ.

#### ถาม: ฉันสามารถลบความคิดเห็นเฉพาะใน Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถลบความคิดเห็นเฉพาะใน Aspose.Words สำหรับ .NET ได้โดยใช้`Comment.Remove` วิธี.

#### ถาม: ฉันจะแก้ไขข้อความของความคิดเห็นที่มีอยู่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการแก้ไขข้อความความคิดเห็นที่มีอยู่ใน Aspose.Words สำหรับ .NET คุณสามารถเข้าถึง`Comment.Text` ทรัพย์สินที่เกี่ยวข้อง`Comment` วัตถุและแก้ไขข้อความตามต้องการ