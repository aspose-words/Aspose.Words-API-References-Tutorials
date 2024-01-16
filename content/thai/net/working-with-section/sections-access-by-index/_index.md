---
title: การเข้าถึงส่วนต่างๆ ตามดัชนี
linktitle: การเข้าถึงส่วนต่างๆ ตามดัชนี
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีเข้าถึงส่วนต่างๆ ของเอกสาร Word ตามดัชนี และเปลี่ยนการตั้งค่าด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/sections-access-by-index/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีเข้าถึงส่วนต่างๆ ของเอกสาร Word ตามดัชนีโดยใช้ไลบรารี Aspose.Words สำหรับ .NET การเข้าถึงส่วนตามดัชนีทำให้คุณสามารถกำหนดเป้าหมายส่วนเฉพาะในเอกสารของคุณและเปลี่ยนการตั้งค่าได้ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ
- เอกสาร Word มีส่วนที่คุณต้องการแก้ไข

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและข้ามไปยังส่วนตามดัชนี
 ต่อไปเราจะโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ระดับ. ในการเข้าถึงส่วนใดส่วนหนึ่งโดยเฉพาะ เราใช้ดัชนีส่วน ในตัวอย่างนี้ เราเข้าถึงส่วนแรกโดยใช้ดัชนี 0

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "Document.docx");

// เข้าถึงส่วนตามดัชนี
Section section = doc.Sections[0];
```

## ขั้นตอนที่ 3: แก้ไขการตั้งค่าส่วน
หากต้องการแก้ไขการตั้งค่าส่วน เราใช้คุณสมบัติของส่วนนั้น`PageSetup` วัตถุ. ในตัวอย่างนี้ เรากำลังเปลี่ยนระยะขอบ ระยะห่างของส่วนหัวและส่วนท้าย และระยะห่างของคอลัมน์ข้อความ

```csharp
section.PageSetup.LeftMargin = 90; // 3.17ซม
section.PageSetup.RightMargin = 90; // 3.17ซม
section.PageSetup.TopMargin = 72; // 2.54ซม
section.PageSetup.BottomMargin = 72; // 2.54ซม
section.PageSetup.HeaderDistance = 35.4; // 1.25ซม
section.PageSetup.FooterDistance = 35.4; // 1.25ซม
section.PageSetup.TextColumns.Spacing = 35.4; // 1.25ซม
```

### ตัวอย่างซอร์สโค้ดสำหรับการเข้าถึงส่วนต่างๆ โดยดัชนีโดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.PageSetup.LeftMargin = 90; // 3.17 ซม
section.PageSetup.RightMargin = 90; // 3.17 ซม
section.PageSetup.TopMargin = 72; // 2.54 ซม
section.PageSetup.BottomMargin = 72; // 2.54 ซม
section.PageSetup.HeaderDistance = 35.4; // 1.25 ซม
section.PageSetup.FooterDistance = 35.4; // 1.25 ซม
section.PageSetup.TextColumns.Spacing = 35.4; // 1.25 ซม

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีเข้าถึงส่วนต่างๆ ของเอกสาร Word ตามดัชนี และเปลี่ยนการตั้งค่าโดยใช้ Aspose.Words สำหรับ .NET การเข้าถึงส่วนตามดัชนีทำให้คุณสามารถกำหนดเป้าหมายและปรับแต่งส่วนเฉพาะในเอกสารของคุณได้ คุณสามารถใช้คุณสมบัตินี้เพื่อตอบสนองความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: จะตั้งค่าไดเร็กทอรีเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณ คุณต้องแทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### ถาม: จะโหลดเอกสารและเข้าถึงส่วนตามดัชนีใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ชั้นเรียนและเข้าถึงส่วนเฉพาะตามดัชนี คุณสามารถใช้รหัสต่อไปนี้:

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "Document.docx");

// เข้าถึงส่วนตามดัชนี
Section section = doc.Sections[0];
```

#### ถาม: ฉันจะเปลี่ยนการตั้งค่าส่วนใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการแก้ไขการตั้งค่าของส่วน คุณสามารถใช้คุณสมบัติของส่วนได้`PageSetup` วัตถุ. ในตัวอย่างนี้ เรากำลังเปลี่ยนระยะขอบ ระยะห่างของส่วนหัวและส่วนท้าย และระยะห่างของคอลัมน์ข้อความ

```csharp
section.PageSetup.LeftMargin = 90; // 3.17ซม
section.PageSetup.RightMargin = 90; // 3.17ซม
section.PageSetup.TopMargin = 72; // 2.54ซม
section.PageSetup.BottomMargin = 72; // 2.54ซม
section.PageSetup.HeaderDistance = 35.4; // 1.25ซม
section.PageSetup.FooterDistance = 35.4; // 1.25ซม
section.PageSetup.TextColumns.Spacing = 35.4; // 1.25ซม
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อคุณแก้ไขการตั้งค่าส่วนแล้ว คุณสามารถบันทึกเอกสารที่แก้ไขลงในไฟล์ได้โดยใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```