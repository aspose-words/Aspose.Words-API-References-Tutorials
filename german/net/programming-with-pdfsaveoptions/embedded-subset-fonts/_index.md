---
title: خطوط المجموعة الفرعية المضمنة
linktitle: خطوط المجموعة الفرعية المضمنة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتضمين مجموعات الخطوط الفرعية في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة تضمين مجموعة الخطوط الفرعية مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تضمين مجموعات فرعية من الخطوط في مستند وإنشاء ملف PDF يحتوي فقط على الحروف الرسومية المستخدمة في المستند.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "Rendering.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات الحفظ كملف PDF

 لإنشاء ملف PDF يحتوي فقط على مجموعات فرعية من الخطوط المستخدمة في المستند ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن مع`EmbedFullFonts` تعيين الخاصية على`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## الخطوة 4: احفظ المستند بصيغة PDF مع مجموعات الخطوط الفرعية

 أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام مجموعات الخطوط الفرعية. حدد اسم ملف الإخراج و`saveOptions` كائن قمنا بتكوينه في الخطوة السابقة.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تضمين مجموعات فرعية من الخطوط في مستند وإنشاء ملف PDF يحتوي فقط على الحروف الرسومية المستخدمة في المستند مع Aspose.Words for .NET.

### عينة من التعليمات البرمجية المصدر لتضمين مجموعات فرعية من الخطوط باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// سيحتوي ملف PDF الناتج على مجموعات فرعية من الخطوط الموجودة في المستند.
	// يتم تضمين الحروف الرسومية المستخدمة في الوثيقة فقط في خطوط PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
