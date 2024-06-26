---
title: สร้างและเพิ่มโหนดย่อหน้า
linktitle: สร้างและเพิ่มโหนดย่อหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: สร้างและเพิ่มโหนดย่อหน้าให้กับเอกสาร Word ของคุณด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-node/create-and-add-paragraph-node/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งแสดงวิธีสร้างและเพิ่มโหนดย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: นำเข้าข้อมูลอ้างอิงที่จำเป็น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าข้อมูลอ้างอิงที่จำเป็นเพื่อใช้ Aspose.Words สำหรับ .NET ในโครงการของคุณ ซึ่งรวมถึงการนำเข้าไลบรารี Aspose.Words และการเพิ่มเนมสเปซที่จำเป็นลงในไฟล์ต้นฉบับของคุณ

```csharp
using Aspose.Words;
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่
 ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่โดยใช้`Document` ชั้นเรียน

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 3: สร้างโหนดย่อหน้า
 ตอนนี้เราจะสร้างโหนดย่อหน้าโดยใช้`Paragraph` คลาสและส่งเอกสารเป็นพารามิเตอร์

```csharp
Paragraph para = new Paragraph(doc);
```

## ขั้นตอนที่ 4: เข้าถึงส่วนเอกสาร
 หากต้องการเพิ่มย่อหน้าลงในเอกสาร เราจำเป็นต้องเข้าถึงส่วนสุดท้ายของเอกสารโดยใช้`LastSection` คุณสมบัติ.

```csharp
Section section = doc.LastSection;
```

## ขั้นตอนที่ 5: เพิ่มโหนดย่อหน้าลงในเอกสาร
 ตอนนี้เรามีส่วนของเอกสารแล้ว เราก็สามารถเพิ่มโหนดย่อหน้าให้กับส่วนได้โดยใช้`AppendChild` วิธีการในส่วน`Body` คุณสมบัติ.

```csharp
section.Body.AppendChild(para);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 สุดท้าย หากต้องการบันทึกเอกสาร คุณสามารถใช้ไฟล์`Save` โดยระบุรูปแบบเอาต์พุตที่ต้องการ เช่น รูปแบบ DOCX

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### ตัวอย่างซอร์สโค้ดสำหรับการสร้างและเพิ่มโหนดย่อหน้าด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

นี่คือตัวอย่างโค้ดที่สมบูรณ์สำหรับการสร้างและเพิ่มโหนดย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ

### คำถามที่พบบ่อย

#### ถาม: โหนดย่อหน้าในเอกสาร XML คืออะไร

ตอบ: โหนดย่อหน้าในเอกสาร XML ใช้เพื่อแสดงย่อหน้าของข้อความ ประกอบด้วยเนื้อหาข้อความของย่อหน้าและสามารถใช้เพื่อจัดโครงสร้างข้อความในเอกสาร XML

#### ถาม: จะสร้างโหนดย่อหน้าใน Node.js ได้อย่างไร

 ตอบ: หากต้องการสร้างโหนดย่อหน้าใน Node.js คุณสามารถใช้ไฟล์`createElement` วิธีการของ`Document` วัตถุเพื่อสร้างองค์ประกอบใหม่ที่มีชื่อ "ย่อหน้า" จากนั้นคุณสามารถใช้`createTextNode` วิธีการสร้างโหนดข้อความที่มีเนื้อหาของย่อหน้า

#### ถาม: จะเพิ่มโหนดย่อหน้าให้กับเอกสาร XML ที่มีอยู่ได้อย่างไร

 ตอบ: หากต้องการเพิ่มโหนดย่อหน้าให้กับเอกสาร XML ที่มีอยู่ คุณสามารถใช้ไฟล์`appendChild`วิธีการเพิ่มโหนดย่อหน้าเป็นลูกขององค์ประกอบอื่นในเอกสาร XML ตัวอย่างเช่น คุณสามารถเพิ่มเป็นรายการย่อยขององค์ประกอบรูทของเอกสารได้

#### ถาม: จะกำหนดเนื้อหาของโหนดย่อหน้าได้อย่างไร

 ตอบ: หากต้องการตั้งค่าเนื้อหาของโหนดย่อหน้า คุณสามารถใช้ไฟล์`createTextNode` วิธีการสร้างโหนดข้อความที่มีเนื้อหาที่ต้องการ จากนั้นใช้ไฟล์`appendChild` วิธีการเพิ่มโหนดข้อความนั้นเป็นลูกของโหนดของย่อหน้า

#### ถาม: ฉันจะจัดรูปแบบข้อความในโหนดย่อหน้าได้อย่างไร

ตอบ: การจัดรูปแบบของข้อความในโหนดย่อหน้าขึ้นอยู่กับ XML API ที่คุณใช้ในสภาพแวดล้อม Node.js ของคุณ โดยปกติคุณสามารถใช้คุณสมบัติและวิธีการเฉพาะเพื่อตั้งค่าแอตทริบิวต์การจัดรูปแบบ เช่น แบบอักษร ขนาด สี ฯลฯ