---
title: حل أسماء الخطوط
linktitle: حل أسماء الخطوط
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لحل أسماء الخطوط المفقودة عند التحويل إلى HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/resolve-font-names/
---

في هذا البرنامج التعليمي ، سنرشدك عبر التعليمات البرمجية المصدر C # لحل أسماء الخطوط المفقودة باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة حل أسماء الخطوط المفقودة تلقائيًا عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل المستند لتتم معالجته. استخدم الكود التالي لتحميل المستند من دليل محدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 هذا الرمز ينشئ مثيل`Document` عن طريق تحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي بتنسيق HTML

سنقوم الآن بتكوين خيارات حفظ HTML لحل أسماء الخطوط المفقودة أثناء التحويل. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions`وتعيين`ResolveFontNames` الخيار ل`true` لحل أسماء الخطوط المفقودة عند التحويل إلى HTML. أيضا ،`PrettyFormat` تم تعيين الخيار إلى`true` للحصول على كود HTML منسق بشكل جيد.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML عن طريق حل أسماء الخطوط المفقودة تلقائيًا ، ويحفظ ملف HTML المحول في الدليل المحدد.

### مثال على شفرة المصدر لحل أسماء الخطوط باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.