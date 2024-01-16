---
title: แทรกย่อหน้าในเอกสาร Word
linktitle: แทรกย่อหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกย่อหน้าที่จัดรูปแบบในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/insert-paragraph/
---
ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีแทรกย่อหน้าลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถเพิ่มย่อหน้าที่จัดรูปแบบลงในเอกสารของคุณได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document และเตรียมใช้งานอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: ตั้งค่าแบบอักษรและการจัดรูปแบบ
ถัดไป ตั้งค่าคุณสมบัติแบบอักษรและการจัดรูปแบบย่อหน้าโดยใช้วัตถุ Font และ ParagraphFormat ตามลำดับ:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## ขั้นตอนที่ 3: แทรกย่อหน้า
หลังจากตั้งค่าแบบอักษรและการจัดรูปแบบแล้ว ให้ใช้เมธอด Writeln ของคลาส DocumentBuilder เพื่อแทรกทั้งย่อหน้า:

```csharp
builder.Writeln("A whole paragraph.");
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
หลังจากแทรกย่อหน้าแล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีการบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## ตัวอย่างซอร์สโค้ดสำหรับการแทรกย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแทรกย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแทรกย่อหน้าที่จัดรูปแบบลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถเพิ่มย่อหน้าที่กำหนดเองด้วยแบบอักษร การจัดรูปแบบ และการจัดแนวเฉพาะลงในเอกสารของคุณได้แล้ว

### คำถามที่พบบ่อยสำหรับการแทรกย่อหน้าในเอกสาร word

#### ถาม: ฉันสามารถแทรกหลายย่อหน้าที่มีรูปแบบต่างกันในเอกสารเดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถแทรกหลายย่อหน้าด้วยการจัดรูปแบบที่แตกต่างกันในเอกสารเดียวกันได้โดยใช้ Aspose.Words สำหรับ .NET เพียงปรับคุณสมบัติการจัดรูปแบบแบบอักษรและย่อหน้าก่อนที่จะเรียก`Writeln` วิธีการในแต่ละย่อหน้า

#### ถาม: ฉันจะตั้งค่าระยะห่างบรรทัดและการเยื้องสำหรับย่อหน้าได้อย่างไร

 ตอบ: Aspose.Words สำหรับ .NET มีตัวเลือกในการตั้งค่าระยะห่างระหว่างบรรทัดและการเยื้องย่อหน้า คุณสามารถปรับ`LineSpacing` และ`LeftIndent` คุณสมบัติของ`ParagraphFormat` วัตถุเพื่อควบคุมด้านเหล่านี้

#### ถาม: เป็นไปได้หรือไม่ที่จะแทรกรายการสัญลักษณ์แสดงหัวข้อย่อยหรือลำดับเลขโดยใช้ DocumentBuilder

 ตอบ: ได้ คุณสามารถสร้างรายการสัญลักษณ์แสดงหัวข้อย่อยหรือลำดับเลขได้โดยการตั้งค่า`ListFormat` คุณสมบัติของ`DocumentBuilder` วัตถุ. คุณสามารถเพิ่มรายการโดยใช้`Writeln` และลักษณะการกำหนดหมายเลขหรือสัญลักษณ์แสดงหัวข้อย่อยจะถูกนำไปใช้โดยอัตโนมัติ

#### ถาม: ฉันสามารถแทรกไฮเปอร์ลิงก์หรือองค์ประกอบอื่นๆ ภายในย่อหน้าได้หรือไม่

 ตอบ: แน่นอน! คุณสามารถแทรกไฮเปอร์ลิงก์ รูปภาพ และองค์ประกอบอื่นๆ ภายในย่อหน้าได้โดยใช้`DocumentBuilder` ระดับ. สิ่งนี้ช่วยให้คุณสร้างเนื้อหาเชิงโต้ตอบที่หลากหลายภายในย่อหน้าของคุณ

#### ถาม: ฉันจะแทรกอักขระพิเศษหรือสัญลักษณ์ในย่อหน้าได้อย่างไร

 ตอบ: หากต้องการแทรกอักขระพิเศษหรือสัญลักษณ์ คุณสามารถใช้`Writeln` วิธีการที่มีการแสดง Unicode ที่ต้องการหรือใช้`InsertSpecialChar` วิธีการของ`DocumentBuilder` ระดับ.