---
title: ปรับเปลี่ยนการตั้งค่าหน้าคำในทุกส่วน
linktitle: ปรับเปลี่ยนการตั้งค่าหน้าคำในทุกส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีแก้ไขการตั้งค่าหน้าคำในทุกส่วนของเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/modify-page-setup-in-all-sections/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีแก้ไขการตั้งค่าหน้าคำในทุกส่วนของเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การเปลี่ยนแปลงการตั้งค่าหน้าอาจรวมถึงการตั้งค่าต่างๆ เช่น ขนาดกระดาษ ระยะขอบ การวางแนว ฯลฯ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและเพิ่มเนื้อหาและส่วนต่างๆ
 ต่อไป เราจะสร้างเอกสารเปล่าโดยสร้างอินสแตนซ์`Document` ชั้นเรียนและที่เกี่ยวข้อง`DocumentBuilder` Constructor เพื่อเพิ่มเนื้อหาและส่วนต่างๆ ให้กับเอกสาร ในตัวอย่างนี้ เรากำลังเพิ่มเนื้อหาและสามส่วน

```csharp
// สร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// เพิ่มเนื้อหาและส่วนต่างๆ
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## ขั้นตอนที่ 3: แก้ไขการตั้งค่าหน้าในทุกส่วน
 หากต้องการเปลี่ยนการตั้งค่าหน้าในทุกส่วนของเอกสาร เราใช้ a`foreach` วนซ้ำเพื่อวนซ้ำแต่ละส่วนและเข้าถึงส่วนต่างๆ`PageSetup` คุณสมบัติ. ในตัวอย่างนี้ เราเปลี่ยนขนาดกระดาษของทุกส่วนโดยตั้งค่าเป็น`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### ตัวอย่างซอร์สโค้ดสำหรับแก้ไขการตั้งค่าหน้า Word ในทุกส่วนโดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// สิ่งสำคัญคือต้องเข้าใจว่าเอกสารสามารถประกอบด้วยหลายส่วน
// และแต่ละส่วนก็มีการตั้งค่าหน้าของตัวเอง ในกรณีนี้ เราต้องการแก้ไขทั้งหมด
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีแก้ไขการตั้งค่าหน้าคำในทุกส่วนของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถเข้าถึงแต่ละส่วนและปรับแต่งการตั้งค่าการกำหนดค่าเพจได้อย่างง่ายดาย คุณสามารถปรับเปลี่ยนและใช้คุณสมบัตินี้เพื่อตอบสนองความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: จะตั้งค่าไดเร็กทอรีเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณ คุณต้องแทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### ถาม: จะสร้างเอกสารและเพิ่มเนื้อหาและส่วนต่างๆ ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสารเปล่าโดยสร้างอินสแตนซ์`Document` ชั้นเรียนและที่เกี่ยวข้อง`DocumentBuilder` Constructor เพื่อเพิ่มเนื้อหาและส่วนต่างๆ ให้กับเอกสาร คุณสามารถใช้โค้ดต่อไปนี้:

```csharp
// สร้างเอกสาร
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// เพิ่มเนื้อหาและส่วนต่างๆ
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder. Writen("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

#### ถาม: จะเปลี่ยนการตั้งค่าหน้าในทุกส่วนใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนการตั้งค่าหน้าในทุกส่วนของเอกสาร คุณสามารถใช้ a`foreach` วนซ้ำเพื่อวนซ้ำแต่ละส่วนและเข้าถึงส่วนต่างๆ`PageSetup` คุณสมบัติ. ในตัวอย่างนี้ เราเปลี่ยนขนาดกระดาษของทุกส่วนโดยตั้งค่าเป็น`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
      section.PageSetup.PaperSize = PaperSize.Letter;
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อคุณเปลี่ยนการตั้งค่าหน้าในทุกส่วนแล้ว คุณสามารถบันทึกเอกสารที่เปลี่ยนแปลงลงในไฟล์โดยใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```