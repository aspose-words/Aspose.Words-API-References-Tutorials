---
title: อย่าบีบอัด Metafiles ขนาดเล็ก
linktitle: อย่าบีบอัด Metafiles ขนาดเล็ก
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อเปิดใช้งานคุณสมบัติ Do Not Compress Small Metafiles เมื่อบันทึกเอกสาร
type: docs
weight: 10
url: /th/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

การบีบอัดข้อมูลเมตาในเอกสารเป็นคุณสมบัติทั่วไปเมื่อประมวลผลคำด้วยไฟล์ในแอปพลิเคชัน C# อย่างไรก็ตาม อาจไม่จำเป็นต้องบีบอัดข้อมูลเมตาของไฟล์ขนาดเล็กเพื่อรักษาคุณภาพ ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีใช้ซอร์สโค้ด C# ของ Aspose.Words for .NET เพื่อเปิดใช้งานฟีเจอร์ "Do Not Compress Small Metafiles" ในตัวเลือกการบันทึกเอกสาร

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีที่มีประสิทธิภาพในการสร้าง แก้ไข แปลง และปกป้องเอกสาร Word ในแพลตฟอร์มต่างๆ รวมถึง .NET มันมีฟีเจอร์มากมายสำหรับการจัดการเอกสาร เช่น การแทรกข้อความ การเปลี่ยนการจัดรูปแบบ การเพิ่มส่วน และอื่นๆ อีกมากมาย

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

ขั้นตอนแรกคือการกำหนดไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร คุณต้องระบุเส้นทางไดเรกทอรีแบบเต็ม ตัวอย่างเช่น :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: แทรกส่วนและข้อความ

จากนั้นคุณสามารถแทรกส่วนและข้อความลงในเอกสารของคุณได้ ใช้คลาส DocumentBuilder จัดทำโดย Aspose.Words เพื่อสร้างเนื้อหาของเอกสารของคุณ นี่เป็นตัวอย่างง่ายๆ:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

ในตัวอย่างนี้ เราสร้างเอกสารเปล่าใหม่ จากนั้นใช้ DocumentBuilder เพื่อเพิ่มบรรทัดข้อความ

## ขั้นตอนที่ 3: ตัวเลือกการตั้งค่า

'การลงทะเบียน

ตอนนี้เรามากำหนดค่าตัวเลือกการบันทึกสำหรับเอกสารของเรากัน ใช้คลาส DocSaveOptions เพื่อระบุการตั้งค่าการบันทึก ตัวอย่างเช่น :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

ในตัวอย่างนี้ เรากำลังสร้างออบเจ็กต์ DocSaveOptions ใหม่เพื่อตั้งค่าตัวเลือกการบันทึก

## ขั้นตอนที่ 4: เปิดใช้งานคุณสมบัติ "อย่าบีบอัด Metafiles ขนาดเล็ก"

 หากต้องการเปิดใช้งานคุณสมบัติ "ห้ามบีบอัดไฟล์เมตาขนาดเล็ก" คุณต้องตั้งค่า`Compliance` คุณสมบัติของวัตถุ DocSaveOptions เป็นค่า`PdfCompliance.PdfA1a`. มีวิธีดังนี้:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

การกำหนดค่านี้ช่วยให้แน่ใจว่าข้อมูลเมตาของไฟล์ขนาดเล็กจะไม่ถูกบีบอัดเมื่อบันทึกเอกสาร

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้าย คุณสามารถบันทึกเอกสารโดยใช้ไฟล์`Save` วิธีการของคลาสเอกสาร ระบุเส้นทางแบบเต็มไปยังไฟล์และชื่อไฟล์ที่ต้องการ ตัวอย่างเช่น :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

อย่าลืมแทนที่ "dataDir" ด้วยเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ

### ตัวอย่างซอร์สโค้ดสำหรับ DocSaveOptions ที่มีคุณสมบัติห้ามบีบอัดไฟล์ Metafiles ขนาดเล็กโดยใช้ Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// แทรกสองส่วนพร้อมข้อความบางส่วน
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// กำหนดค่าตัวเลือกการบันทึกด้วยคุณสมบัติ "อย่าบีบอัดไฟล์เมตาขนาดเล็ก"
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// บันทึกเอกสารด้วยตัวเลือกที่ระบุ
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้อธิบายวิธีใช้ไลบรารี Aspose.Words สำหรับ .NET เพื่อเปิดใช้งานฟีเจอร์ "อย่าบีบอัดไฟล์เมตาขนาดเล็ก" เมื่อบันทึกเอกสาร ด้วยการทำตามขั้นตอนที่ให้ไว้และใช้ซอร์สโค้ด C# ที่ให้มา คุณจะสามารถใช้ฟังก์ชันนี้ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การเก็บรักษาข้อมูลเมตาของไฟล์ขนาดเล็กที่ไม่มีการบีบอัดอาจมีความสำคัญต่อการรักษาคุณภาพและความสมบูรณ์ของเอกสาร