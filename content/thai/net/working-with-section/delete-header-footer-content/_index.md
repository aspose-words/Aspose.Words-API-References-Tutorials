---
title: ลบเนื้อหาส่วนหัวส่วนท้าย
linktitle: ลบเนื้อหาส่วนหัวส่วนท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีลบเนื้อหาส่วนหัวและส่วนท้ายออกจากเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/delete-header-footer-content/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีลบเนื้อหาส่วนหัวและส่วนท้ายออกจากเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การลบเนื้อหาออกจากส่วนหัวและส่วนท้ายจะมีประโยชน์เมื่อคุณต้องการรีเซ็ตหรือลบองค์ประกอบเหล่านี้ออกจากเอกสารของคุณ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ
- เอกสาร Word ที่มีส่วนหัวและส่วนท้ายที่คุณต้องการลบ

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและไปที่ส่วน
 ต่อไปเราจะโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ชั้นเรียน เราจะเข้าถึงส่วนแรกของเอกสารโดยใช้ดัชนี 0

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "Document.docx");

// เข้าถึงส่วน
Section section = doc.Sections[0];
```

## ขั้นตอนที่ 3: ลบเนื้อหาส่วนหัวและส่วนท้าย
 หากต้องการลบเนื้อหาส่วนหัวและส่วนท้ายออกจากส่วน เราจะใช้`ClearHeadersFooters` วิธี.

```csharp
section.ClearHeadersFooters();
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบเนื้อหาส่วนหัวส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เห็นวิธีการลบเนื้อหาส่วนหัวและส่วนท้ายออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การลบเนื้อหาออกจากส่วนหัวและฟุตทำให้คุณสามารถรีเซ็ตหรือลบองค์ประกอบเฉพาะเหล่านั้นออกจากเอกสารของคุณได้ อย่าลังเลที่จะปรับแต่งและใช้คุณสมบัตินี้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อยสำหรับการลบเนื้อหาส่วนหัวส่วนท้าย

#### ถาม: จะตั้งค่าไดเร็กทอรีเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณ คุณต้องแทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### ถาม: จะโหลดเอกสารและส่วนการเข้าถึงใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ชั้นเรียนเรียกว่า`doc` และเข้าถึงส่วนแรกของเอกสารโดยใช้ดัชนี 0 คุณสามารถใช้รหัสต่อไปนี้:

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "Document.docx");

// เข้าถึงส่วน
Section section = doc.Sections[0];
```

#### ถาม: จะลบเนื้อหาส่วนหัวและส่วนท้ายใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อต้องการลบเนื้อหาส่วนหัวและส่วนท้ายออกจากส่วน คุณสามารถใช้`ClearHeadersFooters` วิธี:

```csharp
section.ClearHeadersFooters();
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อคุณลบเนื้อหาส่วนหัวและส่วนท้ายแล้ว คุณสามารถบันทึกเอกสารที่แก้ไขลงในไฟล์โดยใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```