---
title: แทรกเอกสารที่จดหมายเวียน
linktitle: แทรกเอกสารที่จดหมายเวียน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนโดยใช้ฟีเจอร์แทรกเอกสารระหว่างจดหมายเวียนของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและดำเนินการแทรกเอกสาร

## ขั้นตอนที่ 1: กำลังโหลดเอกสารหลัก

ในการเริ่มต้น ให้ระบุไดเร็กทอรีสำหรับเอกสารของคุณและโหลดเอกสารหลักลงในออบเจ็กต์ Document มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## ขั้นตอนที่ 2: กำหนดค่าจดหมายเวียน

ตอนนี้เรามากำหนดค่าจดหมายเวียนและระบุการเรียกกลับผสานฟิลด์เพื่อแทรกเอกสารลงในเอกสารอื่น มีวิธีดังนี้:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## ขั้นตอนที่ 3: การเรียกใช้จดหมายเวียน

เราจะเรียกใช้จดหมายเวียนโดยระบุชื่อของเขตข้อมูลผสานและข้อมูลที่เกี่ยวข้อง มีวิธีดังนี้:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกเอกสารที่จดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์แทรกเอกสารในจดหมายเวียนของ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// เอกสารหลักมีช่องผสานที่เรียกว่า "Document_1"
// ข้อมูลที่เกี่ยวข้องสำหรับฟิลด์นี้มีพาธแบบเต็มไปยังเอกสาร
// ที่ควรแทรกลงในฟิลด์นี้
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

ด้วยรหัสนี้ คุณจะสามารถแทรกเอกสารลงในเอกสารอื่นระหว่างการรวมจดหมายโดยใช้ Aspose.Words สำหรับ .NET เอกสารผลลัพธ์จะถูกบันทึกภายใต้ชื่อใหม่


## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนโดยใช้ฟีเจอร์แทรกเอกสารระหว่างจดหมายเวียนของ Aspose.Words สำหรับ .NET ด้วยการกำหนดค่าจดหมายเวียนและการให้ข้อมูลที่จำเป็น คุณสามารถรวบรวมเอกสารแบบไดนามิกโดยการผสานแม่แบบหรือส่วนเอกสารต่างๆ Aspose.Words สำหรับ .NET มอบวิธีที่ยืดหยุ่นและมีประสิทธิภาพในการจัดการสถานการณ์การสร้างเอกสารที่ซับซ้อน ทำให้เป็นเครื่องมือที่มีค่าสำหรับงานสร้างและจัดการเอกสารโดยอัตโนมัติ

### คำถามที่พบบ่อย

#### ถาม: วัตถุประสงค์ของการแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนคืออะไร

ตอบ: การแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนทำให้คุณสามารถรวมแม่แบบเอกสารหรือส่วนต่างๆ แบบไดนามิกตามข้อมูลที่ให้ไว้ในระหว่างกระบวนการผสาน คุณสมบัตินี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการรวบรวมเอกสารที่ซับซ้อนโดยการผสานเทมเพลตหรือส่วนต่างๆ ที่กำหนดไว้ล่วงหน้าเข้ากับเอกสารขั้นสุดท้าย

#### ถาม: ฉันจะแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อต้องการแทรกเอกสารลงในเอกสารอื่นระหว่างจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:
1. โหลดเอกสารหลักที่จะทำหน้าที่เป็นฐานลงในวัตถุเอกสาร
2. กำหนดค่าจดหมายเวียนและระบุการเรียกกลับผสานฟิลด์เพื่อจัดการการแทรกเอกสาร
3. เรียกใช้จดหมายเวียนด้วยชื่อของเขตข้อมูลผสานและข้อมูลที่เกี่ยวข้อง (เส้นทางไปยังเอกสารที่จะแทรก)

#### ถาม: ฉันจะกำหนดลักษณะการทำงานของการแทรกระหว่างจดหมายเวียนได้อย่างไร

ตอบ: เมื่อต้องการกำหนดลักษณะการทำงานของการแทรกระหว่างจดหมายเวียน คุณสามารถใช้ FieldMergingCallback แบบกำหนดเองได้โดยการสืบทอดจากอินเทอร์เฟซ IFieldMergingCallback สิ่งนี้ช่วยให้คุณควบคุมวิธีการแทรกและรวมเอกสารตามความต้องการเฉพาะของคุณ

#### ถาม: ฉันสามารถแทรกเอกสารหลายชุดระหว่างจดหมายเวียนได้หรือไม่

ตอบ: ได้ คุณสามารถแทรกเอกสารหลายฉบับระหว่างจดหมายเวียนได้ด้วยการให้ข้อมูลที่เหมาะสมสำหรับแต่ละเขตข้อมูลผสาน สำหรับแต่ละเขตข้อมูลผสานที่ต้องมีการแทรกเอกสาร ให้ระบุเส้นทางไปยังเอกสารที่เกี่ยวข้องเป็นข้อมูล

