---
title: ลบข้อมูลส่วนบุคคล
linktitle: ลบข้อมูลส่วนบุคคล
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการลบข้อมูลส่วนบุคคลออกจากเอกสารด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/remove-personal-information/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อลบข้อมูลส่วนบุคคลออกจากเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถลบข้อมูลส่วนบุคคลที่ละเอียดอ่อนออกจากเอกสาร เช่น ข้อมูลประจำตัวผู้เขียน

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะอัปโหลดเอกสาร Word ที่เราต้องการลบข้อมูลส่วนบุคคล ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: ลบข้อมูลส่วนบุคคล

 ตอนนี้เราจะเปิดใช้งานการลบข้อมูลส่วนบุคคลโดยการตั้งค่า`RemovePersonalInformation`ทรัพย์สินเพื่อ`true`. ใช้รหัสต่อไปนี้:

```csharp
doc.RemovePersonalInformation = true;
```

รหัสนี้เปิดใช้งานการลบข้อมูลส่วนบุคคลในเอกสาร

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย เราจะบันทึกเอกสารโดยลบข้อมูลส่วนบุคคลออก ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

รหัสนี้จะบันทึกเอกสารโดยลบข้อมูลส่วนบุคคลไปยังไฟล์ใหม่

### ตัวอย่างซอร์สโค้ดสำหรับการลบข้อมูลส่วนบุคคลโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีลบข้อมูลส่วนบุคคลออกจากเอกสารโดยใช้ Aspose.Words for .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถลบข้อมูลที่ละเอียดอ่อนออกจากเอกสารของคุณเองได้อย่างง่ายดาย