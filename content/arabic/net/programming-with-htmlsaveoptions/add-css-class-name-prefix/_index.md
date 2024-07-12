---
title: أضف بادئة اسم فئة Css
linktitle: أضف بادئة اسم فئة Css
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإضافة بادئة اسم فئة CSS عند تحويل مستند إلى HTML باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لإضافة بادئة اسم فئة CSS باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إضافة بادئة مخصصة لأسماء فئات CSS التي تم إنشاؤها عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد تحويله إلى HTML. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: قم بتعيين خيارات حفظ HTML

لنقم الآن بتعيين خيارات حفظ HTML، بما في ذلك نوع ورقة أنماط CSS وبادئة اسم فئة CSS. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` ومجموعات`CssStyleSheetType` ل`CssStyleSheetType.External`لإنشاء ورقة أنماط CSS خارجية، و`CssClassNamePrefix` ل`"pfx_"` إلى البادئة`"pfx_"` لأسماء فئة CSS.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML المحددة مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML وحفظه في ملف مع إضافة بادئة اسم فئة CSS.

### مثال على التعليمات البرمجية المصدر لإضافة بادئة اسم فئة Css باستخدام Aspose.Words لـ .NET

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

لقد تعلمت الآن كيفية إضافة بادئة اسم فئة CSS عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET. باتباع خطوة الدليل خطوة بخطوة المتوفرة في هذا البرنامج التعليمي، يمكنك تخصيص أسماء فئات CSS في مستندات HTML المحولة.