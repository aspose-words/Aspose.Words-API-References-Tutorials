---
title: ยัติภังค์คำของภาษา
linktitle: ยัติภังค์คำของภาษา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใส่ยัติภังค์คำในภาษาต่างๆ ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-hyphenation/hyphenate-words-of-languages/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีการใส่ยัติภังค์ในภาษาต่างๆ ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดาวน์โหลดและติดตั้งไลบรารี่จากเว็บไซต์อย่างเป็นทางการ

## ขั้นตอนที่ 1: การเริ่มต้นวัตถุเอกสาร

 ขั้นแรกให้เริ่มต้น`Document` วัตถุโดยการระบุเส้นทางไปยังเอกสารต้นฉบับของคุณที่มีข้อความในภาษาต่างๆ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## ขั้นตอนที่ 2: บันทึกพจนานุกรมการใส่ยัติภังค์

จากนั้น ให้บันทึกพจนานุกรมการใส่ยัติภังค์สำหรับภาษาต่างๆ ที่คุณต้องการดำเนินการ ในตัวอย่างนี้ เราลงทะเบียนพจนานุกรมสำหรับภาษาอังกฤษแบบอเมริกันและภาษาเยอรมันสวิส:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

ตรวจสอบให้แน่ใจว่าคุณมีไฟล์พจนานุกรมที่เหมาะสมในไดเร็กทอรีข้อมูลของคุณ

## ขั้นตอนที่ 3: การประมวลผลคำด้วยการใส่ยัติภังค์

 ตอนนี้คุณสามารถใช้คุณสมบัติการใส่ยัติภังค์เพื่อประมวลผลคำในภาษาต่างๆ ได้ คุณสามารถใช้วิธีการที่แตกต่างกันของ`Document` หรือ`DocumentBuilder` ขึ้นอยู่กับความต้องการเฉพาะของคุณ

```csharp
// ตัวอย่าง: การใช้วิธียัติภังค์ของ DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

ดังนั้น ! คุณประมวลผลคำได้สำเร็จด้วยการใส่ยติภังค์ในภาษาต่างๆ ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการใส่ยัติภังค์คำโดยใช้ Aspose.Words สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขให้เหมาะกับความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะพยางค์คำในภาษาใดภาษาหนึ่งด้วย Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการพยางค์คำในภาษาใดภาษาหนึ่งด้วย Aspose.Words คุณสามารถใช้`Hyphenation` ชั้นเรียนและ`Hyphenate()` วิธี. สร้างอินสแตนซ์ของ`Hyphenation` คลาสระบุภาษาที่ต้องการแล้วเรียก`Hyphenate()`วิธีการส่งคำเพื่อพยางค์เป็นอาร์กิวเมนต์ นี่จะทำให้คุณมีพยางค์ของคำในภาษาที่ระบุ

#### ถาม: ฉันควรใช้รหัสภาษาใดเพื่อระบุภาษาของการแสดงพยางค์ใน Aspose.Words

ตอบ: หากต้องการระบุภาษาของพยางค์ใน Aspose.Words คุณต้องใช้รหัสภาษาที่เหมาะสม ตัวอย่างเช่น คุณสามารถใช้ "en" สำหรับภาษาอังกฤษ "fr" สำหรับภาษาฝรั่งเศส "es" สำหรับภาษาสเปน "de" สำหรับภาษาเยอรมัน ฯลฯ ดูเอกสารประกอบของ Aspose.Words สำหรับรายการรหัสภาษาที่รองรับทั้งหมด

#### ถาม: การใช้พยางค์ใช้ได้กับทุกภาษาใน Aspose.Words หรือไม่

ตอบ: การสะกดคำใน Aspose คำจะขึ้นอยู่กับกฎการสะกดคำเฉพาะภาษา แม้ว่า Aspose.Words จะรองรับภาษาได้หลากหลาย แต่บางภาษาอาจไม่รองรับหรืออาจไม่รองรับการออกเสียงพยางค์ ตรวจสอบเอกสารประกอบของ Aspose.Words เพื่อดูว่าภาษาใดบ้างที่รองรับการพยางค์