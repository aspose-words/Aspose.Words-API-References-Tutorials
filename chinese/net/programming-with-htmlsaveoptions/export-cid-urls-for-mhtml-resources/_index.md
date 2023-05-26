---
title: تصدير عناوين Cid لموارد Mhtml
linktitle: تصدير عناوين Cid لموارد Mhtml
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتصدير عناوين URL لـ CID لموارد MHTML عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

في هذا البرنامج التعليمي ، سنرشدك عبر التعليمات البرمجية المصدر C # لتصدير عناوين CID URL لموارد MHTML باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير عناوين URL لمعرف CID لموارد MHTML عند حفظ مستند بتنسيق MHTML.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل المستند للتصدير. استخدم الكود التالي لتحميل المستند من دليل محدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 هذا الرمز ينشئ مثيل`Document` عن طريق تحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي بتنسيق HTML

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير عناوين CID URL لموارد MHTML. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions` مع ضبط تنسيق الحفظ على MHTML. كما يتيح أيضًا تصدير عناوين URL لـ CID لموارد MHTML عن طريق الإعداد`ExportCidUrlsForMhtmlResources` ل`true`.

## الخطوة 4: تحويل وحفظ المستند إلى MHTML

أخيرًا ، سنقوم بتحويل المستند إلى MHTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

يحول هذا الرمز المستند إلى MHTML ويحفظه في ملف يحتوي على عناوين URL لـ CID لموارد MHTML التي تم تصديرها.

### مثال على شفرة المصدر لـ Export Cid Urls For Mhtml Resources باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تصدير عناوين URL لمعرف CID لموارد MHTML عند حفظ مستند بتنسيق MHTML باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إدارة عناوين CID URL في مستندات MHTML التي تم تصديرها.

