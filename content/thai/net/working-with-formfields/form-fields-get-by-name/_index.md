---
title: ฟิลด์ฟอร์มรับตามชื่อ
linktitle: ฟิลด์ฟอร์มรับตามชื่อ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงข้อมูลและแก้ไขฟิลด์แบบฟอร์มตามชื่อในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-formfields/form-fields-get-by-name/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ Aspose.Words สำหรับ .NET เพื่อดึงฟิลด์ฟอร์มตามชื่อจากเอกสาร Word เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดำเนินการ ให้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การเริ่มต้นวัตถุเอกสาร

 ขั้นแรกให้เริ่มต้น`Document` วัตถุโดยระบุเส้นทางไปยังเอกสารต้นฉบับของคุณที่มีเขตข้อมูลแบบฟอร์ม:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## ขั้นตอนที่ 2: การดึงข้อมูลฟิลด์แบบฟอร์ม

 ต่อไปให้เข้าไปที่`FormFields` ทรัพย์สินของ`Range` วัตถุในเอกสารเพื่อดึงข้อมูลเขตข้อมูลแบบฟอร์มทั้งหมด:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

คุณสามารถดึงข้อมูลแบบฟอร์มตามดัชนีหรือตามชื่อ ในตัวอย่างนี้ เราดึงข้อมูลฟิลด์ฟอร์มโดยใช้ทั้งสองวิธี:

```csharp
FormField formField1 = documentFormFields[3]; // การดึงข้อมูลจากดัชนี
FormField formField2 = documentFormFields["Text2"]; // ดึงข้อมูลตามชื่อ
```

## ขั้นตอนที่ 3: การแก้ไขคุณสมบัติของฟิลด์แบบฟอร์ม

เมื่อคุณดึงข้อมูลฟิลด์แบบฟอร์มแล้ว คุณสามารถแก้ไขคุณสมบัติได้ตามต้องการ ในตัวอย่างนี้ เราเปลี่ยนขนาดตัวอักษรเป็น`formField1` ถึง 20 และสีตัวอักษรของ`formField2` เป็นสีแดง:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

แค่นั้นแหละ! คุณได้ดึงข้อมูลฟิลด์ฟอร์มตามชื่อและแก้ไขคุณสมบัติในเอกสาร Word ได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับเขตข้อมูลแบบฟอร์มรับตามชื่อโดยใช้ Aspose.Words สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขได้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะรับฟิลด์แบบฟอร์มตามชื่อใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการรับฟิลด์แบบฟอร์มตามชื่อใน Aspose.Words คุณสามารถใช้`Document.Range.FormFields[name]` วิธี. วิธีการนี้จะส่งคืนฟิลด์แบบฟอร์มที่สอดคล้องกับชื่อที่ระบุ

#### ถาม: จะเกิดอะไรขึ้นหากไม่มีฟิลด์แบบฟอร์มที่มีชื่อที่ระบุอยู่ในเอกสาร

 ตอบ: หากไม่มีฟิลด์แบบฟอร์มตามชื่อที่ระบุในเอกสาร`Document.Range.FormFields[name]` วิธีการจะกลับมา`null`- คุณสามารถตรวจสอบผลลัพธ์นี้เพื่อจัดการกับกรณีที่ไม่พบฟิลด์แบบฟอร์ม

#### ถาม: ฉันจะแก้ไขคุณสมบัติของฟิลด์แบบฟอร์มที่พบได้อย่างไร

ตอบ: เมื่อคุณได้รับฟิลด์แบบฟอร์มตามชื่อแล้ว คุณสามารถเข้าถึงคุณสมบัติแต่ละรายการเพื่อแก้ไขได้ ตัวอย่างเช่น คุณสามารถเปลี่ยนค่าของฟิลด์ เปิดหรือปิดการมองเห็น หรือแก้ไขคุณสมบัติอื่นๆ ได้ตามต้องการ

#### ถาม: ฉันสามารถรับช่องแบบฟอร์มหลายช่องที่มีชื่อเดียวกันในเอกสารได้หรือไม่

 ตอบ: ได้ คุณสามารถมีหลายช่องแบบฟอร์มที่มีชื่อเดียวกันในเอกสารได้ ในกรณีนี้`Document.Range.FormFields[name]` วิธีการจะส่งคืนฟิลด์แบบฟอร์มแรกที่พบกับชื่อที่ระบุ หากคุณมีช่องแบบฟอร์มหลายช่องที่มีชื่อเดียวกัน คุณจะต้องคำนึงถึงเรื่องนี้เมื่อจัดการช่องต่างๆ

#### ถาม: ฉันจะวนซ้ำช่องแบบฟอร์มทั้งหมดในเอกสารได้อย่างไร

 ตอบ: หากต้องการวนซ้ำช่องแบบฟอร์มทั้งหมดในเอกสาร คุณสามารถใช้ a`foreach` วนซ้ำบน`Document.Range.FormFields` ของสะสม. สิ่งนี้จะช่วยให้คุณสามารถเข้าถึงแต่ละฟิลด์ของแบบฟอร์มแยกกันและดำเนินการกับแต่ละฟิลด์ได้