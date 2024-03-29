---
title: โคลนโมดูล Vba จากเอกสาร Word
linktitle: โคลนโมดูล Vba จากเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีโคลนโมดูล VBA จากเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-vba-macros/clone-vba-module/
---

ในบทช่วยสอนนี้ เราจะบอกวิธีโคลนโมดูล VBA จากเอกสาร Word ด้วยมาโครโดยใช้ไลบรารี Aspose.Words สำหรับ .NET การโคลนโมดูล VBA ช่วยให้คุณสามารถใช้ซ้ำหรือคัดลอกโค้ด VBA จากเอกสารต้นฉบับหนึ่งไปยังเอกสารอื่นได้ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ
- เอกสาร Word ที่มีโครงการ VBA พร้อมโมดูลที่คุณต้องการโคลน

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารต้นฉบับ
ต่อไป เราจะโหลดเอกสาร Word ต้นฉบับซึ่งมีโครงการ VBA และโมดูลที่เราต้องการโคลน

```csharp
// โหลดเอกสารต้นทาง
Document doc = new Document(dataDir + "VBA project.docm");
```

## ขั้นตอนที่ 3: สร้างเอกสารใหม่ด้วยโครงการ VBA และโคลนโมดูล
เราจะสร้างเอกสารใหม่ด้วยโครงการ VBA ที่ว่างเปล่าและโคลนโมดูลที่ระบุจากเอกสารต้นฉบับ

```csharp
// สร้างเอกสารใหม่ด้วยโครงการ VBA ที่ว่างเปล่า
Document destDoc = new Document { VbaProject = new VbaProject() };

// โคลนโมดูล
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## ขั้นตอนที่ 4: บันทึกเอกสารปลายทาง
สุดท้าย เราจะบันทึกเอกสารปลายทางด้วยโมดูล VBA ที่โคลนไว้เป็นไฟล์

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### ตัวอย่างซอร์สโค้ดสำหรับโมดูล Clone Vba โดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีการโคลนโมดูล VBA จากเอกสาร Word ด้วยมาโครโดยใช้ Aspose.Words สำหรับ .NET การโคลนโมดูล VBA ช่วยให้คุณสามารถนำโค้ด VBA มาใช้ซ้ำจากเอกสารต้นฉบับหนึ่งในเอกสารอื่นได้อย่างง่ายดาย คุณสามารถใช้คุณสมบัตินี้เพื่อจัดระเบียบและจัดการมาโครของคุณในเอกสารต่างๆ ได้

### คำถามที่พบบ่อย

#### ถาม: การทำซ้ำโมดูล VBA คืออะไร

ตอบ: การทำสำเนาโมดูล VBA ประกอบด้วยการคัดลอกโมดูลที่มีโค้ด VBA จากเอกสาร Word ต้นฉบับไปยังเอกสารอื่น ซึ่งจะทำให้คุณสามารถใช้โค้ด VBA ซ้ำในบริบทต่างๆ หรือแชร์กับเอกสารอื่นๆ ได้

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการโคลนโมดูล VBA จากเอกสาร Word คืออะไร

ตอบ: ก่อนที่คุณจะสามารถโคลนโมดูล VBA จากเอกสาร Word ได้ คุณต้องมีความรู้ในการทำงานของภาษาการเขียนโปรแกรม C# คุณต้องติดตั้งไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณด้วย นอกจากนี้ คุณต้องมีเอกสาร Word ที่มีโครงการ VBA พร้อมด้วยโมดูลที่คุณต้องการโคลน

#### ถาม: จะตั้งค่าไดเร็กทอรีเอกสารในโค้ดได้อย่างไร?

 ตอบ: ในโค้ดที่ให้มา คุณจะต้องแทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีซึ่งเอกสาร Word ของคุณมีโครงการ VBA ตั้งอยู่

#### ถาม: จะบันทึกเอกสารปลายทางด้วยโมดูล VBA ที่ลอกแบบได้อย่างไร

 ตอบ: หากต้องการบันทึกเอกสารปลายทางด้วยโมดูล VBA ที่ลอกแบบมา คุณสามารถใช้ไฟล์`Save` วิธีการของ`Document` โดยระบุเส้นทางปลายทางและชื่อไฟล์ที่ต้องการ