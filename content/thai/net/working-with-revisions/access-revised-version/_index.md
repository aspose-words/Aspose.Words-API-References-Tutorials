---
title: เข้าถึงเวอร์ชันที่แก้ไขแล้ว
linktitle: เข้าถึงเวอร์ชันที่แก้ไขแล้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เข้าถึงเอกสาร Word เวอร์ชันแก้ไขด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/access-revised-version/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีเข้าถึงเอกสาร Word เวอร์ชันที่แก้ไขโดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่มีการแก้ไข

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## ขั้นตอนที่ 2: เข้าถึงเวอร์ชันที่แก้ไขแล้ว

ตอนนี้เราจะไปยังเอกสารฉบับแก้ไขแล้ว

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## ขั้นตอนที่ 3: เรียกดูการแก้ไข

ต่อไป เราจะวนซ้ำการแก้ไขที่มีอยู่ในเอกสารและแสดงข้อมูลเฉพาะสำหรับย่อหน้าที่เป็นรายการ

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### ตัวอย่างซอร์สโค้ดสำหรับการเข้าถึงเวอร์ชันแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเข้าถึงเวอร์ชันที่แก้ไขของเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// สลับไปยังเอกสารเวอร์ชันที่แก้ไข
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเข้าถึงเอกสาร Word เวอร์ชันแก้ไขโดยใช้ Aspose.Words สำหรับ .NET ด้วยการโหลดเอกสาร การนำทางไปยังเวอร์ชันที่แก้ไข และเรียกดูการแก้ไข เราจึงสามารถรับข้อมูลเฉพาะสำหรับย่อหน้าที่เป็นรายการได้ Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่มีประสิทธิภาพสำหรับการจัดการเอกสาร Word รวมถึงการเข้าถึงบทวิจารณ์ ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อเข้าถึงเอกสาร Word ของคุณเวอร์ชันที่แก้ไขแล้วโดยใช้ Aspose.Words for .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะโหลดเอกสารที่มีการแก้ไขลงใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document`คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ที่มีการแก้ไข คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: ฉันจะเข้าถึงเอกสารเวอร์ชันแก้ไขใน Aspose.Words for .NET ได้อย่างไร

 ตอบ: ใช้`RevisionsView` ทรัพย์สินของ`Document` วัตถุเพื่อเข้าถึงเอกสารฉบับแก้ไข คุณสามารถตั้งค่าของ`RevisionsView`ทรัพย์สินเพื่อ`RevisionsView.Final` เพื่อแสดงเวอร์ชันสุดท้ายโดยไม่มีการแก้ไข

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### ถาม: ฉันจะเรียกดูการแก้ไขเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`foreach` วนซ้ำเพื่อวนซ้ำการแก้ไขที่มีอยู่ในเอกสาร คุณสามารถใช้`Revisions` ทรัพย์สินของ`Document` คัดค้านการรับชุดการแก้ไขเอกสารทั้งหมด

```csharp
foreach (Revision revision in doc.Revisions)
{
     // ดำเนินการแก้ไขแต่ละรายการที่นี่
}
```

#### ถาม: จะตรวจสอบได้อย่างไรว่าย่อหน้าเป็นรายการใน Aspose.Words สำหรับ .NET

 ตอบ: ใช้`IsListItem` ทรัพย์สินของ`Paragraph` วัตถุเพื่อตรวจสอบว่าย่อหน้าเป็นรายการหรือไม่ ที่`IsListItem` ผลตอบแทนทรัพย์สิน`true` ถ้าย่อหน้าเป็นรายการ ไม่เช่นนั้นก็จะส่งคืน`false`.

```csharp
if (paragraph.IsListItem)
{
     // ย่อหน้าเป็นรายการ
}
else
{
     // ย่อหน้าไม่ใช่รายการ
}
```