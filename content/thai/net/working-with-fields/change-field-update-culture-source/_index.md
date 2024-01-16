---
title: เปลี่ยนแหล่งที่มาของวัฒนธรรมการอัปเดตฟิลด์
linktitle: เปลี่ยนแหล่งที่มาของวัฒนธรรมการอัปเดตฟิลด์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เปลี่ยนแหล่งที่มาของวัฒนธรรมการอัปเดตฟิลด์ คำแนะนำทีละขั้นตอนเพื่อปรับเปลี่ยนแหล่งที่มาของวัฒนธรรมใน Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/change-field-update-culture-source/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการเปลี่ยนแหล่งวัฒนธรรมการอัปเดตฟิลด์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการปรับเปลี่ยนแหล่งวัฒนธรรม คุณสามารถควบคุมการจัดรูปแบบวันที่ระหว่างการอัปเดตฟิลด์และการดำเนินการจดหมายเวียนได้ เราจะจัดเตรียมซอร์สโค้ด C# ที่จำเป็นและคำแนะนำทีละขั้นตอนเพื่อให้บรรลุเป้าหมายนี้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารและ DocumentBuilder
ในการเริ่มต้น ให้สร้างอินสแตนซ์ของคลาส Document และอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกเนื้อหาด้วยภาษาเฉพาะ
จากนั้น ตั้งค่าภาษาเป็นภาษาเยอรมัน และแทรกฟิลด์ที่มีการจัดรูปแบบวันที่:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

ในโค้ดข้างต้น เราตั้งค่าภาษาแบบอักษรเป็นภาษาเยอรมัน (รหัสสถานที่ 1031) และแทรกสองฟิลด์ด้วยการจัดรูปแบบวันที่ที่ระบุ

## ขั้นตอนที่ 3: เปลี่ยนแหล่งที่มาของวัฒนธรรมการอัปเดตฟิลด์
หากต้องการเปลี่ยนแหล่งที่มาของการอัพเดตฟิลด์ ให้ใช้คลาส FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

ในตัวอย่างนี้ เราตั้งค่าวัฒนธรรมที่ใช้ระหว่างการอัปเดตฟิลด์ให้เลือกจากวัฒนธรรมที่ใช้โดยฟิลด์

## ขั้นตอนที่ 4: ดำเนินการจดหมายเวียน
ดำเนินการจดหมายเวียนและระบุค่าวันที่สำหรับฟิลด์ "Date2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

ในข้อมูลโค้ดนี้ เราดำเนินการดำเนินการจดหมายเวียน และระบุค่า DateTime สำหรับฟิลด์ "Date2"

## ขั้นตอนที่ 5: บันทึกเอกสาร
บันทึกเอกสารที่แก้ไขลงในไฟล์โดยใช้วิธีการบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการเปลี่ยนแหล่งที่มาของวัฒนธรรมการอัพเดตฟิลด์โดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเปลี่ยนแหล่งวัฒนธรรมการอัปเดตฟิลด์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเปลี่ยนแหล่งวัฒนธรรมการอัปเดตฟิลด์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถควบคุมวัฒนธรรมที่ใช้สำหรับการจัดรูปแบบวันที่ระหว่างการอัปเดตฟิลด์และการดำเนินการจดหมายเวียนได้ ปรับแต่งแหล่งที่มาของวัฒนธรรมตามความต้องการของคุณเพื่อให้แน่ใจว่าวันที่ถูกต้องและสม่ำเสมอ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเปลี่ยนแหล่งวัฒนธรรมการอัปเดตฟิลด์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนแหล่งวัฒนธรรมการอัปเดตฟิลด์ใน Aspose.Words สำหรับ .NET คุณสามารถใช้`Document.FieldOptions.CultureSource` คุณสมบัติและตั้งค่าเป็น`FieldCultureSource.FieldCode` หรือ`FieldCultureSource.CurrentThread` . ตัวอย่างเช่นคุณสามารถใช้`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` เพื่อใช้วัฒนธรรมที่กำหนดไว้ในโค้ดฟิลด์

#### ถาม: ฉันจะระบุวัฒนธรรมเฉพาะสำหรับการอัปเดตฟิลด์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการระบุวัฒนธรรมเฉพาะสำหรับการอัปเดตฟิลด์ใน Aspose.Words สำหรับ .NET คุณสามารถใช้`Document.FieldOptions.FieldUpdateCultureInfo` คุณสมบัติและตั้งค่า`CultureInfo` วัตถุที่สอดคล้องกับวัฒนธรรมที่ต้องการ ตัวอย่างเช่นคุณสามารถใช้`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` เพื่อระบุวัฒนธรรมฝรั่งเศส (ฝรั่งเศส)

#### ถาม: เป็นไปได้หรือไม่ที่จะปิดใช้งานการอัปเดตฟิลด์อัตโนมัติใน Aspose.Words สำหรับ .NET

 ตอบ: ได้ คุณสามารถปิดใช้งานการอัปเดตฟิลด์อัตโนมัติใน Aspose.Words for .NET ได้ คุณสามารถใช้`Document.FieldOptions.UpdateFields` คุณสมบัติและตั้งค่าเป็น`false` เพื่อป้องกันไม่ให้ฟิลด์อัปเดตอัตโนมัติ สิ่งนี้ช่วยให้คุณควบคุมการอัปเดตฟิลด์ด้วยตนเองได้ตามต้องการ

#### ถาม: ฉันจะอัปเดตฟิลด์เอกสารใน Aspose.Words สำหรับ .NET ด้วยตนเองได้อย่างไร

 ตอบ: หากต้องการอัปเดตฟิลด์ในเอกสารใน Aspose.Words สำหรับ .NET ด้วยตนเอง คุณสามารถใช้`Field.Update` วิธีการสำหรับแต่ละสาขาแยกกัน ตัวอย่างเช่นคุณสามารถใช้`field.Update()` เพื่ออัพเดตฟิลด์เฉพาะ