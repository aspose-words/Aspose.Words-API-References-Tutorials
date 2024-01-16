---
title: แปลง Metafiles เป็น Emf หรือ Wmf
linktitle: แปลง Metafiles เป็น Emf หรือ Wmf
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแปลงไฟล์เมตาเป็นรูปแบบ EMF หรือ WMF เมื่อแปลงเอกสารเป็น HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อแปลงเมตาไฟล์เป็นรูปแบบ EMF หรือ WMF ด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถแปลงรูปภาพในรูปแบบ metafile เป็นรูปแบบที่เข้ากันได้มากขึ้น เช่น EMF หรือ WMF เมื่อแปลงเอกสารเป็น HTML

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การแทรกรูปภาพลงในเอกสาร

ในขั้นตอนนี้ เราจะแทรกรูปภาพลงในเอกสารที่จะแปลง ใช้โค้ดต่อไปนี้เพื่อแทรกรูปภาพจากแหล่งข้อมูลโดยใช้แท็ก HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 รหัสนี้สร้างอินสแตนซ์ของ`Document` และ`DocumentBuilder` เพื่อสร้างเอกสาร มันแทรก`<img>` แท็กลงในเอกสารด้วยรูปภาพที่เข้ารหัส base64

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึก HTML

ตอนนี้เราจะตั้งค่าตัวเลือกการบันทึก HTML รวมถึงรูปแบบไฟล์เมตาที่จะใช้สำหรับรูปภาพ ใช้รหัสต่อไปนี้:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 รหัสนี้สร้างอินสแตนซ์ของ`HtmlSaveOptions` และชุด`MetafileFormat` ถึง`HtmlMetafileFormat.EmfOrWmf` เพื่อระบุว่าควรแปลง metafiles เป็นรูปแบบ EMF หรือ WMF เมื่อแปลงเป็น HTML

## ขั้นตอนที่ 4: การแปลงและบันทึกเอกสารเป็น HTML

ในที่สุดเราจะแปลงเอกสารเป็น HTML โดยใช้ตัวเลือกบันทึก HTML ที่กำหนดไว้ก่อนหน้านี้ ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

รหัสนี้จะแปลงเอกสารเป็น HTML และบันทึกลงในไฟล์ที่มี metafiles ที่แปลงแล้วในรูปแบบ EMF หรือ WMF ขึ้นอยู่กับตัวเลือกการบันทึกที่ตั้งไว้

### ตัวอย่างซอร์สโค้ดสำหรับการแปลง Metafiles เป็น Emf หรือ Wmf โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีแปลง metafiles เป็นรูปแบบ EMF หรือ WMF เมื่อแปลงเอกสารเป็น HTML โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถจัดการเมตาไฟล์ในเอกสาร HTML ที่แปลงแล้วของคุณได้อย่างง่ายดาย