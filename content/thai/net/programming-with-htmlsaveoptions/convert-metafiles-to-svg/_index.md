---
title: แปลง Metafiles เป็น Svg
linktitle: แปลง Metafiles เป็น Svg
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแปลงไฟล์เมตาเป็นรูปแบบ SVG เมื่อแปลงเอกสารเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อแปลงเมตาไฟล์เป็นรูปแบบ SVG ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถแปลง metafiles เป็นรูปแบบ SVG เมื่อแปลงเอกสารเป็น HTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การแทรกรูปภาพ SVG ลงในเอกสาร

ในขั้นตอนนี้ เราจะแทรกรูปภาพ SVG ลงในเอกสารที่จะแปลง ใช้โค้ดต่อไปนี้เพื่อแทรกรูปภาพ SVG โดยใช้แท็ก HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 รหัสนี้สร้างอินสแตนซ์ของ`Document`และ`DocumentBuilder` เพื่อสร้างเอกสาร มันแทรกก`<svg>` แท็กที่มี`<polygon>` องค์ประกอบพร้อมแอตทริบิวต์เพื่อกำหนดรูปร่างและสไตล์ของรูปภาพ SVG

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึก HTML

ตอนนี้เราจะตั้งค่าตัวเลือกการบันทึก HTML โดยระบุว่าควรแปลงไฟล์เมตาเป็นรูปแบบ SVG ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และชุด`MetafileFormat` ถึง`HtmlMetafileFormat.Svg` เพื่อระบุว่าควรแปลง metafiles เป็นรูปแบบ SVG เมื่อแปลงเป็น HTML

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

สุดท้ายนี้ เราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกการบันทึก HTML ที่กำหนดไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML และบันทึกเป็นไฟล์ที่มี metafiles แปลงเป็น SVG

### ตัวอย่างซอร์สโค้ดสำหรับการแปลง Metafiles เป็น Svg โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
