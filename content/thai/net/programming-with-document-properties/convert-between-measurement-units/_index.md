---
title: แปลงระหว่างหน่วยการวัด
linktitle: แปลงระหว่างหน่วยการวัด
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแปลงระหว่างหน่วยการวัดในเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/convert-between-measurement-units/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อแปลงระหว่างหน่วยการวัดด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถระบุระยะขอบ ระยะส่วนหัวและส่วนท้าย ฯลฯ ในหน่วยการวัดที่แตกต่างกัน

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสารและตัวสร้าง

ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่และเริ่มต้นตัวสร้าง ใช้รหัสต่อไปนี้:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: กำหนดค่าหน่วยการวัด

ตอนนี้เราจะแปลงค่าระยะขอบ ระยะส่วนหัวและส่วนท้าย ฯลฯ ในหน่วยการวัดที่แตกต่างกัน ใช้รหัสต่อไปนี้เพื่อระบุค่าในหน่วยการวัดเฉพาะ:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 รหัสนี้ใช้`ConvertUtil` คลาสของ Aspose.Words เพื่อแปลงค่าที่ระบุเป็นนิ้ว (`InchToPoint` คุณยังสามารถใช้วิธีการแปลงอื่น ๆ ที่มีอยู่ใน`ConvertUtil` คลาสเพื่อแปลงค่าเป็นหน่วยการวัดอื่น

### ตัวอย่างซอร์สโค้ดสำหรับการแปลงระหว่างหน่วยการวัดโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

ตอนนี้ คุณได้เรียนรู้วิธีการแปลงระหว่างหน่วยการวัดเมื่อระบุระยะขอบ ระยะห่างของส่วนหัวและส่วนท้าย ฯลฯ ในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถระบุค่าในหน่วยการวัดที่ต้องการในเอกสารของคุณเองได้อย่างง่ายดาย