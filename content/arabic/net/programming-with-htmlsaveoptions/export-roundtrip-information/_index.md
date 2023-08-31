---
title: تصدير معلومات الرحلة ذهابًا وإيابًا
linktitle: تصدير معلومات الرحلة ذهابًا وإيابًا
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير معلومات ذهابًا وإيابًا عند حفظ مستند بتنسيق HTML باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتصدير معلومات ذهابًا وإيابًا من مستند باستخدام Aspose.Words for .NET. تسمح لك هذه الميزة بتضمين معلومات ذهابًا وإيابًا في ملف HTML الذي تم تصديره، مما يسهل استرداد التغييرات التي تم إجراؤها على المستند الأصلي.

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

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير معلومات المستند ذهابًا وإيابًا. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions`ويحدد`ExportRoundtripInformation` خيار ل`true` لتضمين معلومات رحلة الذهاب والإياب عند التصدير.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML بما في ذلك معلومات رحلة الذهاب والإياب، ويحفظ ملف HTML الذي تم تصديره إلى الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لتصدير معلومات Roundtrip باستخدام Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.