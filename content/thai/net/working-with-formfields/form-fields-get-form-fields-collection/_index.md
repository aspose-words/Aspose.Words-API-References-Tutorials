---
title: ฟิลด์ฟอร์ม รับคอลเลกชั่นฟิลด์ฟอร์ม
linktitle: ฟิลด์ฟอร์ม รับคอลเลกชั่นฟิลด์ฟอร์ม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงข้อมูลและจัดการคอลเลกชันฟิลด์แบบฟอร์มในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-formfields/form-fields-get-form-fields-collection/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ Aspose.Words สำหรับ .NET เพื่อดึงชุดฟิลด์ฟอร์มจากเอกสาร Word เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดำเนินการ ให้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การเริ่มต้นวัตถุเอกสาร

 ขั้นแรกให้เริ่มต้น`Document` วัตถุโดยระบุเส้นทางไปยังเอกสารต้นฉบับของคุณที่มีเขตข้อมูลแบบฟอร์ม:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## ขั้นตอนที่ 2: การดึงข้อมูลคอลเลกชันเขตข้อมูลแบบฟอร์ม

 ต่อไปให้เข้าไปที่`FormFields` ทรัพย์สินของ`Range` วัตถุในเอกสารเพื่อดึงข้อมูลคอลเลกชันของเขตข้อมูลแบบฟอร์ม:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 ตอนนี้ คุณมีคอลเลกชันของฟิลด์ฟอร์มจากเอกสาร Word ที่จัดเก็บไว้ใน`formFields` ตัวแปร.

## ขั้นตอนที่ 3: การเข้าถึงและการจัดการฟิลด์แบบฟอร์ม

คุณสามารถวนซ้ำคอลเลกชันฟิลด์แบบฟอร์มและดำเนินการต่างๆ ในแต่ละฟิลด์ฟอร์ม เช่น การรับหรือตั้งค่า การแก้ไขการจัดรูปแบบ หรือการดึงข้อมูล

```csharp
foreach (FormField formField in formFields)
{
    // เข้าถึงและจัดการฟิลด์แบบฟอร์มแต่ละฟิลด์
    // -
}
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารที่แก้ไขหากจำเป็น:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

แค่นั้นแหละ! คุณได้ดึงข้อมูลคอลเลกชันของฟิลด์แบบฟอร์มจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับ Form Fields รับ Form Fields Collection โดยใช้ Aspose.Words สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// เข้าถึงและจัดการฟิลด์แบบฟอร์มตามต้องการ
// -

doc.Save(dataDir + "ModifiedFormFields.docx");
```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขได้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเข้าถึงคอลเลกชันฟิลด์แบบฟอร์มใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการเข้าถึงคอลเลกชันของฟิลด์แบบฟอร์มใน Aspose.Words คุณสามารถใช้`Document.FormFields` คุณสมบัติ. คุณสมบัตินี้ส่งคืนคอลเลกชันที่สมบูรณ์ของฟิลด์แบบฟอร์มที่มีอยู่ในเอกสาร

#### ถาม: ฉันจะวนซ้ำช่องแบบฟอร์มและดำเนินการกับแต่ละช่องได้อย่างไร

 ตอบ: คุณสามารถวนซ้ำผ่านช่องแบบฟอร์มโดยใช้`foreach` วนซ้ำบน`Document.FormFields` ของสะสม. ในการวนซ้ำแต่ละครั้ง คุณสามารถเข้าถึงคุณสมบัติและดำเนินการเฉพาะบนฟิลด์แบบฟอร์มได้

#### ถาม: ฉันสามารถกรองคอลเลกชันฟิลด์แบบฟอร์มเพื่อรับเฉพาะฟิลด์บางประเภทได้หรือไม่

ตอบ: ได้ คุณสามารถกรองคอลเลกชันฟิลด์แบบฟอร์มได้โดยใช้เงื่อนไขที่เหมาะสมในการวนซ้ำของคุณ ตัวอย่างเช่น คุณสามารถตรวจสอบประเภทฟิลด์ของแต่ละรายการและดำเนินการเฉพาะในฟิลด์ที่ตรงกับเกณฑ์ของคุณเท่านั้น

#### ถาม: ฉันจะลบฟิลด์แบบฟอร์มเฉพาะออกจากคอลเลกชันได้อย่างไร

 ตอบ: หากต้องการลบฟิลด์ฟอร์มเฉพาะออกจากคอลเลกชัน คุณสามารถใช้`FormField.Remove` วิธีการระบุฟิลด์ที่คุณต้องการลบ วิธีนี้จะลบฟิลด์แบบฟอร์มออกจากคอลเลกชัน

#### ถาม: เป็นไปได้ไหมที่จะแก้ไขคุณสมบัติของฟิลด์แบบฟอร์มใน Aspose.Words

ตอบ: ได้ คุณสามารถเปลี่ยนคุณสมบัติของเขตข้อมูลแบบฟอร์มใน Aspose.Words ได้โดยการเข้าถึงคุณสมบัติแต่ละรายการ ตัวอย่างเช่น คุณสามารถเปลี่ยนชื่อ ค่า หรือตัวเลือกของฟิลด์ฟอร์มโดยใช้คุณสมบัติที่เหมาะสม