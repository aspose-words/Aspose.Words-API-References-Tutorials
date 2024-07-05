---
title: รับประเภทคำแก้ไข
linktitle: รับประเภทคำแก้ไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: รับประเภทคำแก้ไขในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/get-revision-types/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะบอกวิธีรับประเภทการแก้ไขคำในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่มีการแก้ไข

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ขั้นตอนที่ 2: ก้าวผ่านย่อหน้า

ต่อไป เราจะดูย่อหน้าต่างๆ ของเอกสารและตรวจสอบประเภทของคำที่แก้ไขที่เกี่ยวข้องกับแต่ละย่อหน้า

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับรับประเภทการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับรับประเภทการแก้ไขในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับการแก้ไขประเภทคำในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราทำตามขั้นตอนในการโหลดเอกสาร อ่านย่อหน้าต่างๆ และตรวจสอบประเภทของคำวิจารณ์ที่เกี่ยวข้องกับแต่ละย่อหน้า ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อวิเคราะห์บทวิจารณ์คำในเอกสาร Word ของคุณเองโดยใช้ Aspose.Words for .NET

### คำถามที่พบบ่อยเพื่อรับประเภทคำแก้ไข

#### ถาม: จะอัพโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document` คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: ฉันจะวนซ้ำย่อหน้าในเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Paragraphs` คุณสมบัติของส่วนเอกสารเพื่อรับการรวบรวมย่อหน้า จากนั้นคุณสามารถใช้การวนซ้ำเพื่อวนซ้ำแต่ละย่อหน้าได้

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // ประมวลผลแต่ละย่อหน้าที่นี่
}
```

#### ถาม: จะตรวจสอบได้อย่างไรว่าย่อหน้าถูกย้าย (ลบ) ใน Aspose.Words สำหรับ .NET หรือไม่

 ตอบ: ใช้ย่อหน้า`IsMoveFromRevision`คุณสมบัติเพื่อตรวจสอบว่ามีการย้าย (ลบ) หรือไม่

```csharp
if (paragraph. IsMove

FromRevision)
{
     // ย่อหน้าถูกย้าย (ลบแล้ว)
}
```

#### ถาม: จะตรวจสอบได้อย่างไรว่าย่อหน้าถูกย้าย (แทรก) ใน Aspose.Words สำหรับ .NET หรือไม่

 ตอบ: ใช้ย่อหน้า`IsMoveToRevision` คุณสมบัติเพื่อตรวจสอบว่ามีการย้ายหรือไม่ (แทรก)

```csharp
if (paragraph.IsMoveToRevision)
{
     // ย่อหน้าถูกย้ายแล้ว (แทรก)
}
```