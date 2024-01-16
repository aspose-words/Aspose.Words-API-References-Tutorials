---
title: แสดงการแก้ไขในบอลลูน
linktitle: แสดงการแก้ไขในบอลลูน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: แสดงการแก้ไขในบอลลูนด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/show-revisions-in-balloons/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีแสดงการแก้ไขในบอลลูนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่มีการแก้ไข

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการแสดงบทวิจารณ์

เราจะกำหนดค่าตัวเลือกการแสดงเพื่อให้มองเห็นการแก้ไขในบอลลูน

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## ขั้นตอนที่ 3: บันทึกเอกสารในรูปแบบ PDF

สุดท้ายนี้ เราจะบันทึกเอกสารเป็น PDF โดยมีการแก้ไขแสดงในบอลลูน

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## รูปแบบเอาต์พุตมาร์กดาวน์

สามารถจัดรูปแบบเอาต์พุตเป็นมาร์กดาวน์ได้เพื่อปรับปรุงให้อ่านง่ายขึ้น ตัวอย่างเช่น :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### ตัวอย่างซอร์สโค้ดสำหรับแสดงการแก้ไขในบอลลูนโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อแสดงการแก้ไขในบอลลูนในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// เรนเดอร์แทรกการแก้ไขแบบอินไลน์ ลบ และจัดรูปแบบการแก้ไขในบอลลูน
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// แสดงแถบแก้ไขทางด้านขวาของหน้า
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแสดงการแก้ไขในบอลลูนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการใช้ตัวเลือกการแสดงผลที่เหมาะสม เราจึงสามารถทำให้การแก้ไขมองเห็นได้ในฟองอากาศโดยมีแถบการแก้ไขทางด้านขวา Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่มีประสิทธิภาพมากมายสำหรับการจัดการเอกสาร Word รวมถึงการจัดการการแก้ไข ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อแสดงการแก้ไขในบอลลูนในเอกสาร Word ของคุณเองโดยใช้ Aspose.Words สำหรับ .NET


### คำถามที่พบบ่อย

#### ถาม: จะอัพโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document` คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: จะแสดงการแก้ไขในบอลลูนด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`ShowInBalloons` ทรัพย์สินของ`RevisionOptions` วัตถุเพื่อกำหนดค่าการแสดงผลการแก้ไขในบอลลูน คุณสามารถตั้งค่าคุณสมบัตินี้ได้`ShowInBalloons.FormatAndDelete` เพื่อแสดงการแก้ไขในบอลลูนพร้อมการลบและการแก้ไขการจัดรูปแบบ

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### ถาม: จะบันทึกเอกสารในรูปแบบ PDF ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสารในรูปแบบ PDF คุณต้องระบุเส้นทางปลายทางแบบเต็มด้วยนามสกุล ".pdf"

```csharp
doc.Save("path/to/destination/document.pdf");
```