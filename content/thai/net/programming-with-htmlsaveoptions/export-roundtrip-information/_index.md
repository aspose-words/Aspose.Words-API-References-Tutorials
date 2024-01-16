---
title: ส่งออกข้อมูลไปกลับ
linktitle: ส่งออกข้อมูลไปกลับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการส่งออกข้อมูลไปกลับเมื่อบันทึกเอกสารเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อส่งออกข้อมูลไปกลับจากเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถรวมข้อมูลไปกลับในไฟล์ HTML ที่ส่งออก ทำให้ง่ายต่อการเรียกข้อมูลการเปลี่ยนแปลงที่ทำกับเอกสารต้นฉบับ

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

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อส่งออกข้อมูลไปกลับของเอกสาร ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions`และตั้งค่า`ExportRoundtripInformation` ตัวเลือกในการ`true` เพื่อรวมข้อมูลไปกลับเมื่อส่งออก

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้าย เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML รวมถึงข้อมูลไปกลับ และบันทึกไฟล์ HTML ที่ส่งออกไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับส่งออกข้อมูลไปกลับโดยใช้ Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.