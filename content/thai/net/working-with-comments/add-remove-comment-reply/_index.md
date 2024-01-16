---
title: เพิ่ม ลบการตอบกลับความคิดเห็น
linktitle: เพิ่ม ลบการตอบกลับความคิดเห็น
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มและลบการตอบกลับความคิดเห็นในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-comments/add-remove-comment-reply/
---

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีเพิ่มและลบการตอบกลับความคิดเห็นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถจัดการการตอบกลับความคิดเห็นและปรับแต่งได้ตามความต้องการของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: โหลดเอกสาร
ในการเริ่มต้น ให้โหลดเอกสารที่มีความคิดเห็นโดยใช้คลาสเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## ขั้นตอนที่ 2: เข้าถึงความคิดเห็นและจัดการการตอบกลับ
จากนั้น เข้าถึงความคิดเห็นจากเอกสารโดยใช้วิธี GetChild ด้วยพารามิเตอร์ NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

หากต้องการลบการตอบกลับออกจากความคิดเห็น ให้ใช้เมธอด RemoveReply และระบุดัชนีการตอบกลับที่ต้องการ:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

หากต้องการเพิ่มการตอบกลับความคิดเห็นใหม่ ให้ใช้เมธอด AddReply และระบุชื่อผู้เขียน ชื่อย่อผู้เขียน วันที่และเวลา และข้อความตอบกลับ:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
หลังจากเพิ่มหรือลบการตอบกลับความคิดเห็น ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มและลบการตอบกลับความคิดเห็นโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเพิ่มและลบการตอบกลับความคิดเห็นโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มและลบการตอบกลับความคิดเห็นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถจัดการการตอบกลับความคิดเห็นและปรับแต่งได้ตามความต้องการของคุณ

การตอบกลับความคิดเห็นช่วยให้สามารถพูดคุยและแสดงความคิดเห็นร่วมกันภายในเอกสารได้ ทดลองใช้ผู้เขียนตอบกลับ ชื่อย่อ วันที่ และข้อความต่างๆ เพื่อปรับปรุงการทำงานร่วมกันและการสื่อสารภายในเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเพิ่มความคิดเห็นใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเพิ่มความคิดเห็นใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Comment.AddComment` วิธีการระบุข้อความความคิดเห็นและตำแหน่งที่คุณต้องการเพิ่มลงในเอกสาร

#### ถาม: ฉันจะลบความคิดเห็นใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการลบความคิดเห็นใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Comment.Remove` วิธีการระบุ`Comment` วัตถุที่คุณต้องการลบ

#### ถาม: ฉันสามารถตอบกลับความคิดเห็นใน Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถตอบกลับความคิดเห็นใน Aspose.Words for .NET ได้โดยใช้`Comment.AddReply` วิธีการระบุข้อความตอบกลับและตำแหน่งที่คุณต้องการเพิ่มลงในเอกสาร

#### ถาม: ฉันจะเข้าถึงความคิดเห็นที่มีอยู่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถเข้าถึงความคิดเห็นที่มีอยู่ใน Aspose.Words for .NET ได้โดยใช้`CommentCollection` ทรัพย์สินของ`Document`วัตถุ. ซึ่งจะช่วยให้คุณสามารถเรียกดูความคิดเห็นทั้งหมดที่มีอยู่ในเอกสารได้

#### ถาม: ฉันสามารถแก้ไขข้อความความคิดเห็นใน Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขข้อความแสดงความคิดเห็นใน Aspose.Words for .NET ได้โดยเข้าไปที่`Comment.Text` ทรัพย์สินที่เกี่ยวข้อง`Comment` วัตถุและแก้ไขข้อความตามต้องการ