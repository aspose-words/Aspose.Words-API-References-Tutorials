---
title: ยอมรับการแก้ไข
linktitle: ยอมรับการแก้ไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธียอมรับการแก้ไขเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/accept-revisions/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการยอมรับการแก้ไขเอกสาร Word โดยใช้ฟีเจอร์ยอมรับการแก้ไขของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและยอมรับการเปลี่ยนแปลงในเอกสาร

## ขั้นตอนที่ 1: การเพิ่มและแก้ไขเนื้อหาเอกสาร

ในตัวอย่างนี้ เรากำลังสร้างเอกสารและเพิ่มเนื้อหา เราใช้หลายย่อหน้าเพื่อแสดงการเปลี่ยนแปลงและการแก้ไข มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// เพิ่มข้อความในย่อหน้าแรก จากนั้นเพิ่มอีกสองย่อหน้า
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## ขั้นตอนที่ 2: ติดตามบทวิจารณ์และเพิ่มบทวิจารณ์

เราเปิดใช้งานการติดตามการแก้ไขและเพิ่มการแก้ไขให้กับเอกสาร มีวิธีดังนี้:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// ย่อหน้านี้เป็นเพียงการแก้ไขและจะมีการตั้งค่าสถานะ "IsInsertRevision" ที่สอดคล้องกัน
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## ขั้นตอนที่ 3: ลบย่อหน้าและจัดการการแก้ไข

เราลบย่อหน้าและตรวจสอบการแก้ไขที่บันทึกไว้ มีวิธีดังนี้:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// ขณะที่เรากำลังติดตามการแก้ไข ย่อหน้านั้นยังคงอยู่ในเอกสาร โดยจะมีการตั้งค่าสถานะ "IsDeleteRevision"
// และจะแสดงเป็นบทวิจารณ์ใน Microsoft Word จนกว่าเราจะยอมรับหรือปฏิเสธบทวิจารณ์ทั้งหมด
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## ขั้นตอนที่ 4: ยอมรับการเปลี่ยนแปลง

เรายอมรับการเปลี่ยนแปลงเอกสารทั้งหมด มีวิธีดังนี้:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## ขั้นตอนที่ 5: หยุดการติดตามบทวิจารณ์

เราจะหยุดการติดตามการแก้ไข เพื่อให้การเปลี่ยนแปลงในเอกสารไม่แสดงเป็นการแก้ไขอีกต่อไป มีวิธีดังนี้:

```csharp
doc.StopTrackRevisions();
```
## ขั้นตอนที่ 6: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับยอมรับการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการยอมรับการเปลี่ยนแปลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:


```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// เพิ่มข้อความในย่อหน้าแรก จากนั้นเพิ่มอีกสองย่อหน้า
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//เรามีสามย่อหน้า ซึ่งไม่มีรายการใดที่ถือเป็นการแก้ไขประเภทใดๆ
// หากเราเพิ่ม/ลบเนื้อหาใดๆ ในเอกสารขณะติดตามการแก้ไข
// สิ่งเหล่านี้จะแสดงในเอกสารและสามารถยอมรับ/ปฏิเสธได้
doc.StartTrackRevisions("John Doe", DateTime.Now);

// ย่อหน้านี้เป็นเพียงการแก้ไขและจะมีการตั้งค่าสถานะตาม "IsInsertRevision"
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// รับคอลเลกชันย่อหน้าของเอกสารและลบย่อหน้า
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// เนื่องจากเรากำลังติดตามการแก้ไข ย่อหน้านั้นยังคงอยู่ในเอกสาร โดยจะมีการตั้งค่า "IsDeleteRevision"
// และจะแสดงเป็นการแก้ไขใน Microsoft Word จนกว่าเราจะยอมรับหรือปฏิเสธการแก้ไขทั้งหมด
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// ย่อหน้าการแก้ไขการลบจะถูกลบออกเมื่อเรายอมรับการเปลี่ยนแปลง
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// การหยุดการติดตามการแก้ไขทำให้ข้อความนี้ปรากฏเป็นข้อความปกติ
// การแก้ไขจะไม่นับเมื่อมีการเปลี่ยนแปลงเอกสาร
doc.StopTrackRevisions();

// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธียอมรับการแก้ไขในเอกสาร Word โดยใช้ฟีเจอร์ยอมรับการแก้ไขของ Aspose.Words สำหรับ .NET เราได้ทำตามขั้นตอนเพื่อเพิ่มและแก้ไขเนื้อหาเอกสาร ติดตามการแก้ไข ลบย่อหน้าที่แก้ไข ยอมรับการเปลี่ยนแปลงทั้งหมด และหยุดติดตามการแก้ไข ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อจัดการการแก้ไขในเอกสาร Word ของคุณเองได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเปิดใช้งานการติดตามการแก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

#### โซลูชันที่ 1:

 ตอบ: หากต้องการเปิดใช้งานการติดตามการแก้ไขใน Aspose.Words สำหรับ .NET ให้ใช้`StartTrackRevisions` วิธีการของ`Document` วัตถุและระบุชื่อผู้เขียนและวันที่เริ่มต้นสำหรับการติดตามการแก้ไข

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### โซลูชันที่ 2:

 ตอบ: คุณยังสามารถเปิดใช้งานการติดตามการแก้ไขโดยใช้`Document` ตัวสร้างที่ยอมรับ`trackRevisions` และ`author` พารามิเตอร์

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### ถาม: จะยอมรับการเปลี่ยนแปลงทั้งหมดในเอกสารด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`AcceptAllRevisions` วิธีการของ`Document` คัดค้านการยอมรับการเปลี่ยนแปลงทั้งหมดที่ทำกับเอกสาร

```csharp
doc.AcceptAllRevisions();
```

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขด้วยการแก้ไขที่ยอมรับได้อย่างไร

 ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสารที่แก้ไขพร้อมการแก้ไขที่ยอมรับ ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่ถูกต้อง

```csharp
doc.Save("path/to/the/document.docx");
```

#### ถาม: ฉันจะหยุดการติดตามการแก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`StopTrackRevisions` วิธีการของ`Document` คัดค้านเพื่อหยุดการแก้ไขการติดตาม

```csharp
doc.StopTrackRevisions();
```

#### ถาม: ฉันจะลบย่อหน้าที่แก้ไขในเอกสารด้วย Aspose.Words for .NET ได้อย่างไร

 ตอบ: หากต้องการลบย่อหน้าที่แก้ไขในเอกสาร คุณสามารถใช้`Remove` วิธีการรวบรวมย่อหน้า

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```