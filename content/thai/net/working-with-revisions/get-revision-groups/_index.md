---
title: รับกลุ่มการแก้ไข
linktitle: รับกลุ่มการแก้ไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: รับกลุ่มการแก้ไขในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/get-revision-groups/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะบอกวิธีรับกลุ่มการแก้ไขในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่มีการแก้ไข

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ขั้นตอนที่ 2: เรียกดูกลุ่มการแก้ไข

ต่อไป เราจะวนดูกลุ่มการแก้ไขที่มีอยู่ในเอกสารและแสดงรายละเอียด เช่น ผู้แต่ง ประเภทการแก้ไข และข้อความที่แก้ไข

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### ตัวอย่างซอร์สโค้ดสำหรับรับกลุ่มการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อรับกลุ่มการแก้ไขในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับกลุ่มการแก้ไขในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราทำตามขั้นตอนในการโหลดเอกสารและเรียกดูกลุ่มบทวิจารณ์ โดยแสดงรายละเอียด เช่น ผู้แต่งและประเภทบทวิจารณ์ ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อวิเคราะห์การแก้ไขเอกสาร Word ของคุณเองโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: จะอัพโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document` คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: จะเรียกดูกลุ่มการแก้ไขในเอกสารใน Aspose.Words for .NET ได้อย่างไร

 ตอบ: ใช้`Groups` คุณสมบัติของเอกสาร`Revisions`วัตถุเพื่อรับการรวบรวมกลุ่มการแก้ไข จากนั้นคุณสามารถใช้การวนซ้ำเพื่อวนซ้ำกลุ่มการตรวจทานแต่ละกลุ่มได้

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // ประมวลผลกลุ่มตรวจสอบแต่ละกลุ่มที่นี่
}
```

#### ถาม: จะรับผู้เขียนกลุ่มบทวิจารณ์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Author` ทรัพย์สินของ`RevisionGroup` คัดค้านเพื่อรับผู้เขียนกลุ่มแก้ไข

```csharp
string author = group.Author;
```

#### ถาม: จะรับประเภทการแก้ไขของกลุ่มการแก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`RevisionType` ทรัพย์สินของ`RevisionGroup` วัตถุเพื่อรับประเภทการแก้ไขของกลุ่ม

```csharp
string revisionType = group.RevisionType;
```