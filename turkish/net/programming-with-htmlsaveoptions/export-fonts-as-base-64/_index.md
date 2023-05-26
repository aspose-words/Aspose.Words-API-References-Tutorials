---
title: تصدير الخطوط كقاعدة 64
linktitle: تصدير الخطوط كقاعدة 64
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتصدير خطوط 64 أساسية عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتصدير 64 خطًا أساسيًا باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير الخطوط كبيانات أساسية 64 عند حفظ مستند بتنسيق HTML.

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

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير 64 خطًا أساسيًا. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions` ومجموعات`ExportFontsAsBase64` ل`true` لتحديد أن الخطوط يجب أن يتم تصديرها كبيانات أساسية 64 عند الحفظ بتنسيق HTML.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML ويحفظه في ملف بالخطوط المصدرة كبيانات أساسية 64.

### مثال على شفرة المصدر لـ Export Fonts As Base 64 باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تصدير خطوط أساسية 64 عند حفظ مستند بتنسيق HTML باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تصدير الخطوط بأمان ودمجها في مستندات HTML الخاصة بك.