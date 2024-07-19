---
title: แก้ไขชื่อแบบอักษร
linktitle: แก้ไขชื่อแบบอักษร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแก้ไขชื่อแบบอักษรที่หายไปเมื่อแปลงเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/resolve-font-names/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อแก้ไขชื่อแบบอักษรที่หายไปด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณแก้ไขชื่อแบบอักษรที่หายไปได้โดยอัตโนมัติเมื่อแปลงเอกสารเป็น HTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสารที่จะประมวลผล ใช้รหัสต่อไปนี้เพื่อโหลดเอกสารจากไดเร็กทอรีที่ระบุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 รหัสนี้สร้างอินสแตนซ์ของ`Document` โดยการโหลดเอกสารจากไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการสำรองข้อมูล HTML

ตอนนี้เราจะกำหนดค่าตัวเลือกการบันทึก HTML เพื่อแก้ไขชื่อแบบอักษรที่หายไประหว่างการแปลง ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และตั้งค่า`ResolveFontNames` ตัวเลือกในการ`true`เพื่อแก้ไขชื่อแบบอักษรที่หายไปเมื่อแปลงเป็น HTML นอกจากนี้`PrettyFormat` ตัวเลือกถูกตั้งค่าเป็น`true` เพื่อให้ได้โค้ด HTML ที่มีรูปแบบสวยงาม

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้าย เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดค่าไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML โดยแก้ไขชื่อแบบอักษรที่หายไปโดยอัตโนมัติ และบันทึกไฟล์ HTML ที่แปลงแล้วไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับการแก้ไขชื่อแบบอักษรโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.