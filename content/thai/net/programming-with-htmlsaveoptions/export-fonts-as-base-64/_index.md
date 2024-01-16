---
title: ส่งออกแบบอักษรเป็นฐาน 64
linktitle: ส่งออกแบบอักษรเป็นฐาน 64
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการส่งออกแบบอักษร 64 ฐานเมื่อบันทึกเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อส่งออกฟอนต์ฐาน 64 ด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถส่งออกแบบอักษรเป็นข้อมูลฐาน 64 เมื่อบันทึกเอกสารในรูปแบบ HTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสารที่จะส่งออก ใช้รหัสต่อไปนี้เพื่อโหลดเอกสารจากไดเร็กทอรีที่ระบุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 รหัสนี้สร้างอินสแตนซ์ของ`Document` โดยการโหลดเอกสารจากไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการสำรองข้อมูล HTML

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อส่งออกแบบอักษรฐาน 64 ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และชุด`ExportFontsAsBase64` ถึง`true` เพื่อระบุว่าควรส่งออกแบบอักษรเป็นข้อมูลฐาน 64 เมื่อบันทึกเป็น HTML

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้าย เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML และบันทึกลงในไฟล์ที่มีแบบอักษรส่งออกเป็นข้อมูลฐาน 64

### ตัวอย่างซอร์สโค้ดสำหรับส่งออกแบบอักษรเป็นฐาน 64 โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีส่งออกแบบอักษรฐาน 64 เมื่อบันทึกเอกสารเป็น HTML โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถส่งออกแบบอักษรอย่างปลอดภัยและฝังอยู่ในเอกสาร HTML ของคุณได้อย่างง่ายดาย