---
title: ระบุสถานที่ในระดับฟิลด์
linktitle: ระบุสถานที่ในระดับฟิลด์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีระบุการแปลระดับฟิลด์ในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/specify-locale-at-field-level/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้ ซึ่งอนุญาตให้ระบุการแปลในระดับฟิลด์โดยใช้คุณลักษณะ Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words ไว้ในโปรเจ็กต์ของคุณก่อนที่จะใช้โค้ดนี้

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกเอกสารที่แก้ไข

## ขั้นตอนที่ 2: สร้างตัวสร้างเอกสาร

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 ที่นี่เรากำลังสร้างอินสแตนซ์ของ`DocumentBuilder` คลาสที่จะช่วยให้เราสามารถเพิ่มฟิลด์ลงในเอกสารได้

## ขั้นตอนที่ 3: แทรกฟิลด์วันที่พร้อมตำแหน่งเฉพาะ

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 เราใช้ตัวสร้างเอกสารเพื่อแทรกฟิลด์ประเภท`FieldType.FieldDate` ลงในเอกสาร โดยการตั้งค่า`LocaleId`ทรัพย์สินเพื่อ`1049`เราระบุการแปลภาษารัสเซียสำหรับฟิลด์นี้

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขพร้อมตำแหน่งที่ระบุลงในไฟล์ที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับระบุการแปลระดับฟิลด์ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

นี่คือตัวอย่างซอร์สโค้ดเพื่อระบุการแปลในระดับฟิลด์ในเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้โค้ดนี้เพื่อแทรกช่องวันที่พร้อมตำแหน่งเฉพาะในเอกสาร Word ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะระบุภาษาระดับฟิลด์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุภาษาที่ระดับฟิลด์ใน Aspose.Words สำหรับ .NET คุณสามารถใช้รูปแบบ`FieldOptions` ชั้นเรียนและมัน`FieldLocale` คุณสมบัติเพื่อกำหนดสถานที่ที่ต้องการ ตัวอย่างเช่นคุณสามารถใช้`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` เพื่อระบุตำแหน่งที่ตั้งของฝรั่งเศส (ฝรั่งเศส)

#### ถาม: เป็นไปได้ไหมที่จะระบุภาษาที่แตกต่างกันสำหรับแต่ละฟิลด์ใน Aspose.Words สำหรับ .NET

 ตอบ: ได้ คุณสามารถระบุภาษาที่แตกต่างกันสำหรับแต่ละฟิลด์ใน Aspose.Words สำหรับ .NET ได้ คุณสามารถใช้`FieldOptions.FieldLocale` คุณสมบัติก่อนที่จะสร้างหรืออัปเดตฟิลด์เฉพาะเพื่อกำหนดภาษาอื่น

#### ถาม: ฉันจะรับตำแหน่งที่ใช้อยู่ในปัจจุบันสำหรับฟิลด์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการรับโลแคลที่ใช้อยู่ในปัจจุบันสำหรับฟิลด์ใน Aspose.Words สำหรับ .NET คุณสามารถใช้ฟิลด์`Field.LocaleId`คุณสมบัติ. สิ่งนี้จะช่วยให้คุณได้รับตัวระบุสถานที่ที่เกี่ยวข้องกับฟิลด์