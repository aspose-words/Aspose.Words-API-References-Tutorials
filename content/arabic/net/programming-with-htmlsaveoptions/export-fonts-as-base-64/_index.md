---
title: تصدير الخطوط كقاعدة 64
linktitle: تصدير الخطوط كقاعدة 64
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير الخطوط الأساسية 64 عند حفظ مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لتصدير الخطوط الأساسية البالغ عددها 64 خطًا باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير الخطوط كبيانات أساسية 64 عند حفظ مستند بتنسيق HTML.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل المستند للتصدير. استخدم الكود التالي لتحميل المستند من دليل محدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 يقوم هذا الرمز بإنشاء مثيل لـ`Document` عن طريق تحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ HTML

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير الخطوط الأساسية البالغ عددها 64 خطًا. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` ومجموعات`ExportFontsAsBase64` ل`true` لتحديد الخطوط التي يجب تصديرها كبيانات أساسية 64 عند الحفظ بتنسيق HTML.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML وحفظه في ملف بالخطوط المصدرة كبيانات أساسية 64.

### مثال على التعليمات البرمجية المصدر لـ Export Fonts As Base 64 باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تصدير الخطوط الأساسية 64 عند حفظ مستند بتنسيق HTML باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تصدير الخطوط بشكل آمن ومضمنة في مستندات HTML الخاصة بك.