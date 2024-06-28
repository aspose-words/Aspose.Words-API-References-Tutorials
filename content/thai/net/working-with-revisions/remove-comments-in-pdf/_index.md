---
title: ลบความคิดเห็นในไฟล์ PDF
linktitle: ลบความคิดเห็นในไฟล์ PDF
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ลบความคิดเห็นในไฟล์ PDF ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/remove-comments-in-pdf/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะบอกวิธีลบความคิดเห็นในไฟล์ PDF โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการโหลดเอกสารที่มีความคิดเห็น

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ขั้นตอนที่ 2: ซ่อนความคิดเห็นในรูปแบบ PDF

เราจะกำหนดค่าตัวเลือกเค้าโครงเพื่อซ่อนความคิดเห็นเมื่อสร้าง PDF

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## ขั้นตอนที่ 3: บันทึกเอกสารเป็น PDF

สุดท้ายเราจะบันทึกเอกสารในรูปแบบ PDF โดยการลบความคิดเห็น

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## รูปแบบเอาต์พุตมาร์กดาวน์

สามารถจัดรูปแบบเอาต์พุตเป็นมาร์กดาวน์ได้เพื่อปรับปรุงให้อ่านง่ายขึ้น ตัวอย่างเช่น :

```markdown
- Comments are hidden in the generated PDF.
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบความคิดเห็นในรูปแบบ Pdf โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อลบความคิดเห็นในไฟล์ PDF โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// ซ่อนความคิดเห็นในรูปแบบ PDF
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีลบความคิดเห็นออกจากไฟล์ PDF โดยใช้ Aspose.Words สำหรับ .NET ด้วยการใช้ตัวเลือกเค้าโครงที่เหมาะสม เราสามารถซ่อนความคิดเห็นเมื่อสร้าง PDF ได้ Aspose.Words สำหรับ .NET มอบความยืดหยุ่นอย่างมากในการจัดการไฟล์ Word และแปลงเป็นรูปแบบต่างๆ รวมถึง PDF ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อลบความคิดเห็นในไฟล์ PDF ของคุณเองโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อยสำหรับการลบความคิดเห็นในไฟล์ pdf

#### ถาม: จะอัพโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document` คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: จะซ่อนความคิดเห็นใน PDF ที่สร้างด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`CommentDisplayMode` ทรัพย์สินของ`LayoutOptions` วัตถุเพื่อกำหนดค่าวิธีการแสดงความคิดเห็นเมื่อสร้าง PDF หากต้องการซ่อนความคิดเห็น ให้ตั้งค่าคุณสมบัตินี้เป็น`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### ถาม: จะบันทึกเอกสารเป็น PDF ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสารในรูปแบบ PDF ระบุเส้นทางแบบเต็มของไฟล์ PDF

```csharp
doc.Save("path/to/the/file.pdf");
```