---
title: เพิ่มคำนำหน้าชื่อคลาส Css
linktitle: เพิ่มคำนำหน้าชื่อคลาส Css
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเพิ่มคำนำหน้าชื่อคลาส CSS เมื่อแปลงเอกสารเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อเพิ่มคำนำหน้าชื่อคลาส CSS ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเพิ่มคำนำหน้าที่กำหนดเองให้กับชื่อคลาส CSS ที่สร้างขึ้นเมื่อแปลงเอกสารเป็น HTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการแปลงเป็น HTML ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
//พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึก HTML

ตอนนี้เรามาตั้งค่าตัวเลือกการบันทึก HTML รวมถึงประเภทสไตล์ชีต CSS และคำนำหน้าชื่อคลาส CSS ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และชุด`CssStyleSheetType` ถึง`CssStyleSheetType.External` เพื่อสร้างสไตล์ชีต CSS ภายนอกและ`CssClassNamePrefix` ถึง`"pfx_"` เพื่อนำหน้า`"pfx_"` เพื่อตั้งชื่อคลาส CSS

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้ายนี้ เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML และบันทึกลงในไฟล์โดยเพิ่มคำนำหน้าชื่อคลาส CSS

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มคำนำหน้าชื่อคลาส Css โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีเพิ่มคำนำหน้าชื่อคลาส CSS เมื่อแปลงเอกสารเป็น HTML โดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถปรับแต่งชื่อคลาส CSS ในเอกสาร HTML ที่แปลงแล้วของคุณได้