---
title: ส่งออกทรัพยากร
linktitle: ส่งออกทรัพยากร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการส่งออกทรัพยากรเอกสารเมื่อบันทึกเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-resources/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อส่งออกทรัพยากรเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถส่งออกทรัพยากร เช่น แบบอักษร เป็นไฟล์ภายนอก เมื่อบันทึกเอกสารในรูปแบบ HTML

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

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อส่งออกทรัพยากรเอกสาร ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และตั้งค่าตัวเลือกต่อไปนี้:

- `CssStyleSheetType` ถูกตั้งค่าเป็น`CssStyleSheetType.External`เพื่อส่งออกสไตล์ชีต CSS ไปยังไฟล์ภายนอก
- `ExportFontResources` ถูกตั้งค่าเป็น`true` เพื่อส่งออกทรัพยากรแบบอักษร
- `ResourceFolder` ระบุไดเร็กทอรีปลายทางที่จะบันทึกทรัพยากร
- `ResourceFolderAlias` ระบุนามแฝง URL ที่จะใช้ในการเข้าถึงทรัพยากร

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้าย เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML และบันทึกทรัพยากรลงในไดเร็กทอรีที่ระบุ โดยใช้นามแฝง URL ที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับส่งออกทรัพยากรโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.