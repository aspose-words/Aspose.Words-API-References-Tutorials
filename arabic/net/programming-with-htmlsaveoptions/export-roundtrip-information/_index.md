---
title: تصدير معلومات رحلة الذهاب والإياب
linktitle: تصدير معلومات رحلة الذهاب والإياب
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتصدير معلومات الرحلة ذهابًا وإيابًا عند حفظ مستند بتنسيق HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتصدير معلومات رحلة الذهاب والعودة من مستند مع Aspose.Words for .NET. تتيح لك هذه الميزة تضمين معلومات رحلة الذهاب والإياب في ملف HTML المُصدَّر ، مما يسهل استرداد التغييرات التي تم إجراؤها على المستند الأصلي.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل المستند للتصدير. استخدم الكود التالي لتحميل المستند من دليل محدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 هذا الرمز ينشئ مثيل`Document` عن طريق تحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي بتنسيق HTML

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير معلومات الرحلة ذهابًا وإيابًا الخاصة بالمستند. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions`وتعيين`ExportRoundtripInformation` الخيار ل`true` لتضمين معلومات رحلة الذهاب والإياب عند التصدير.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML بما في ذلك معلومات الرحلة ذهابًا وإيابًا ، ويحفظ ملف HTML الذي تم تصديره إلى الدليل المحدد.

### مثال على شفرة المصدر لتصدير معلومات رحلة الذهاب والإياب باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.