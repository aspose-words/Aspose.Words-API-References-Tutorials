---
title: ส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความ
linktitle: ส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความธรรมดาด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความธรรมดาด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความที่อ่านได้ แทนที่จะส่งออกเป็นองค์ประกอบอินพุต HTML

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

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความธรรมดา ใช้รหัสต่อไปนี้:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// โฟลเดอร์ที่ระบุต้องมีอยู่และว่างเปล่า
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions`และตั้งค่า`ExportTextInputFormFieldAsText` ตัวเลือกในการ`true` เพื่อส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความธรรมดา นอกจากนี้ยังระบุโฟลเดอร์ที่จะบันทึกภาพที่แยกออกมา

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้าย เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML โดยส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความธรรมดา และบันทึกไฟล์ HTML ที่ส่งออกไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับฟิลด์แบบฟอร์มป้อนข้อความส่งออกเป็นข้อความโดยใช้ Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// โฟลเดอร์ที่ระบุต้องมีอยู่และควรว่างเปล่า
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// ตั้งค่าตัวเลือกเพื่อส่งออกช่องแบบฟอร์มเป็นข้อความธรรมดา ไม่ใช่องค์ประกอบอินพุต HTML
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.