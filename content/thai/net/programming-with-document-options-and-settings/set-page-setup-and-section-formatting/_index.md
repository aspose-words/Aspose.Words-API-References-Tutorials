---
title: ตั้งค่าการตั้งค่าหน้าและการจัดรูปแบบส่วน
linktitle: ตั้งค่าการตั้งค่าหน้าและการจัดรูปแบบส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าเค้าโครงของเอกสารและการจัดรูปแบบส่วนด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อตั้งค่าเค้าโครงและการจัดรูปแบบส่วนด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถตั้งค่าการวางแนวหน้า ระยะขอบ และขนาดกระดาษได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสาร

ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่ ใช้รหัสต่อไปนี้เพื่อสร้างเอกสารและเตรียมใช้งานตัวสร้าง:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

## ขั้นตอนที่ 3: การตั้งค่าเค้าโครงและบันทึกเอกสาร

ตอนนี้เรามากำหนดค่าเค้าโครงเอกสารกันดีกว่า ใช้รหัสต่อไปนี้เพื่อตั้งค่าการวางแนว ระยะขอบ และขนาดกระดาษ:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

รหัสนี้จะตั้งค่าการวางแนวหน้าเป็นแนวนอน ขอบซ้ายเป็น 50 และขนาดกระดาษเป็น 10x14

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าการตั้งค่าหน้าและการจัดรูปแบบส่วนโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสารใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีกำหนดค่าเค้าโครงและการจัดรูปแบบส่วนของเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถปรับแต่งเค้าโครงและการจัดรูปแบบของเอกสารของคุณเองได้อย่างง่ายดาย