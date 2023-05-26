---
title: تخطي الخطوط المضمنة Arial و Times Roman Fonts
linktitle: تخطي الخطوط المضمنة Arial و Times Roman Fonts
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي لإنشاء ملف PDF بدون تضمين خطوط Arial و Times Roman باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام الميزة لتخطي خطوط Arial و Times Roman المضمنة إلى حجم ملف التعريف باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تكوين خيار وضع دمج الخط في مستند وإنشاء ملف PDF بدون تضمين خطوط Arial و Times Roman.

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

## الخطوة 3: تكوين خيارات الحفظ كملف PDF مع دمج الخط

 لتخطي تضمين خطوط Arial و Times Roman في ملف PDF الذي تم إنشاؤه ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن وتعيين`FontEmbeddingMode` ملكية ل`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## الخطوة 4: احفظ المستند كملف PDF بدون خطوط مضمنة

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في إنشاء ملف PDF بدون تضمين خطوط Arial و Times Roman باستخدام Aspose.Words for .NET.

### مثال على كود المصدر لتخطي خطوط Arial و Times Roman المضمنة بحجم ملف التعريف باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
