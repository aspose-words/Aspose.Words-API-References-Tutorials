---
title: ความคิดเห็นได้รับการแก้ไขแล้วและตอบกลับ
linktitle: ความคิดเห็นได้รับการแก้ไขแล้วและตอบกลับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแก้ไขความคิดเห็นและการตอบกลับในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-comments/comment-resolved-and-replies/
---

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีแก้ไขความคิดเห็นและการตอบกลับในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถจัดการการแก้ไขความคิดเห็นและอัปเดตสถานะของความคิดเห็นและการตอบกลับได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: โหลดเอกสารและเข้าถึงความคิดเห็น
ในการเริ่มต้น ให้โหลดเอกสารที่มีความคิดเห็นโดยใช้คลาส Document และเข้าถึงคอลเลกชันความคิดเห็น:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## ขั้นตอนที่ 2: แก้ไขความคิดเห็นและการตอบกลับของพวกเขา
จากนั้น ย้ำความคิดเห็นและการตอบกลับของพวกเขาเพื่อทำเครื่องหมายว่าแก้ไขแล้ว:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

ในโค้ดข้างต้น เราเข้าถึงความคิดเห็นของผู้ปกครองและทำซ้ำผ่านการตอบกลับ เราสามารถดึงข้อมูล ID ความคิดเห็นหลักและสถานะการแก้ไขได้ จากนั้น เราจะอัปเดตเครื่องหมาย "เสร็จสิ้น" ของการตอบกลับความคิดเห็นแต่ละรายการเพื่อระบุวิธีแก้ปัญหา

## ขั้นตอนที่ 3: บันทึกเอกสาร
หลังจากแก้ไขความคิดเห็นและอัปเดตสถานะแล้ว ให้บันทึกเอกสารที่แก้ไขลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแก้ไขความคิดเห็นและการตอบกลับโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแก้ไขความคิดเห็นและการตอบกลับโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
อย่าลืมปรับโค้ดตามความต้องการเฉพาะของคุณ รวมถึงเส้นทางไฟล์เอกสารและการปรับแต่งเพิ่มเติม

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแก้ไขความคิดเห็นและการตอบกลับในเอกสาร Word โดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถจัดการการแก้ไขความคิดเห็นและอัปเดตสถานะของความคิดเห็นและการตอบกลับได้ตามความต้องการของคุณ

การแก้ไขปัญหาความคิดเห็นช่วยในการติดตามและจัดการคำติชมภายในเอกสาร ทดลองใช้สถานะความคิดเห็นต่างๆ และปรับแต่งเพื่อปรับปรุงการทำงานร่วมกันและตรวจสอบกระบวนการในเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะแก้ไขความคิดเห็นใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการแก้ไขความคิดเห็นใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Comment.Resolve` วิธีการระบุ`Comment` วัตถุที่คุณต้องการแก้ไข การดำเนินการนี้จะทำเครื่องหมายความคิดเห็นว่าแก้ไขแล้ว และซ่อนไว้ในเอกสารขั้นสุดท้าย

#### ถาม: ฉันจะเพิ่มการตอบกลับไปยังความคิดเห็นที่ได้รับการแก้ปัญหาใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: แม้ว่าความคิดเห็นที่ได้รับการแก้ปัญหาแล้วจะถูกซ่อนไว้ตามค่าเริ่มต้นในเอกสารขั้นสุดท้าย คุณยังคงสามารถเพิ่มการตอบกลับความคิดเห็นที่ได้รับการแก้ปัญหาแล้วได้โดยใช้`Comment.AddReply` วิธีการระบุข้อความตอบกลับและตำแหน่งที่คุณต้องการเพิ่ม

#### ถาม: ฉันจะดูความคิดเห็นที่ได้รับการแก้ปัญหาใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ตามค่าเริ่มต้น ความคิดเห็นที่ได้รับการแก้ปัญหาจะถูกซ่อนอยู่ในเอกสารขั้นสุดท้าย อย่างไรก็ตาม คุณสามารถแสดงได้โดยใช้`CommentOptions.ShowResolvedComments` ทรัพย์สินของ`Document` วัตถุและตั้งค่าเป็น`true`.

#### ถาม: ฉันจะซ่อนความคิดเห็นทั้งหมด รวมถึงการตอบกลับใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการซ่อนความคิดเห็นทั้งหมด รวมถึงการตอบกลับใน Aspose.Words สำหรับ .NET คุณสามารถใช้`CommentOptions.CommentDisplayMode` ทรัพย์สินของ`Document` วัตถุและตั้งค่าเป็น`CommentDisplayMode.None`.

#### ถาม: ฉันสามารถแก้ไขข้อความของความคิดเห็นที่ได้รับการแก้ปัญหาใน Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขข้อความของความคิดเห็นที่ได้รับการแก้ปัญหาใน Aspose.Words for .NET ได้โดยเข้าไปที่`Comment.Text` ทรัพย์สินที่เกี่ยวข้อง`Comment` วัตถุและแก้ไขข้อความตามต้องการ