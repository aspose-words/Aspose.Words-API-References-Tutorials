---
title: ส่งออก Cid Urls สำหรับทรัพยากร Mhtml
linktitle: ส่งออก Cid Urls สำหรับทรัพยากร Mhtml
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการส่งออก CID URL ของทรัพยากร MHTML เมื่อบันทึกเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อส่งออก CID URL สำหรับทรัพยากร MHTML ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถส่งออก CID URL ของทรัพยากร MHTML เมื่อบันทึกเอกสารในรูปแบบ MHTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสารที่จะส่งออก ใช้รหัสต่อไปนี้เพื่อโหลดเอกสารจากไดเร็กทอรีที่ระบุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 รหัสนี้สร้างอินสแตนซ์ของ`Document` โดยการโหลดเอกสารจากไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการสำรองข้อมูล HTML

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อส่งออก CID URL ของทรัพยากร MHTML ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` โดยกำหนดรูปแบบการบันทึกเป็น MHTML นอกจากนี้ยังเปิดใช้งานการส่งออก CID URL ของทรัพยากร MHTML โดยการตั้งค่า`ExportCidUrlsForMhtmlResources` ถึง`true`.

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น MHTML

สุดท้ายนี้ เราจะแปลงเอกสารเป็น MHTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น MHTML และบันทึกลงในไฟล์ที่มี CID URL ของทรัพยากร MHTML ที่ส่งออก

### ตัวอย่างซอร์สโค้ดสำหรับส่งออก Cid Urls สำหรับทรัพยากร Mhtml โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีส่งออก CID URL ของทรัพยากร MHTML เมื่อบันทึกเอกสารในรูปแบบ MHTML โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถจัดการ CID URL ในเอกสาร MHTML ที่ส่งออกของคุณได้อย่างง่ายดาย

