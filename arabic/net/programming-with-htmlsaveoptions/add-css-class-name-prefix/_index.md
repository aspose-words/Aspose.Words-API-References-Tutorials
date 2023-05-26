---
title: أضف بادئة اسم فئة Css
linktitle: أضف بادئة اسم فئة Css
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإضافة بادئة اسم فئة CSS عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لإضافة بادئة اسم فئة CSS مع Aspose.Words for .NET. تتيح لك هذه الميزة إضافة بادئة مخصصة لأسماء فئات CSS التي تم إنشاؤها عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد تحويله إلى HTML. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: تعيين خيارات حفظ HTML

لنقم الآن بتعيين خيارات حفظ HTML ، بما في ذلك نوع ورقة أنماط CSS وبادئة اسم فئة CSS. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions` ومجموعات`CssStyleSheetType` ل`CssStyleSheetType.External` لإنشاء ورقة أنماط CSS خارجية ، و`CssClassNamePrefix` ل`"pfx_"`للبادئة`"pfx_"` لتسمية فئة CSS.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML المحددة مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML ويحفظه في ملف مع إضافة بادئة اسم فئة CSS.

### مثال على شفرة المصدر لإضافة بادئة اسم فئة Css باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إضافة بادئة اسم فئة CSS عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET. باتباع خطوة الدليل خطوة بخطوة المتوفرة في هذا البرنامج التعليمي ، يمكنك تخصيص أسماء فئات CSS في مستندات HTML المحولة.