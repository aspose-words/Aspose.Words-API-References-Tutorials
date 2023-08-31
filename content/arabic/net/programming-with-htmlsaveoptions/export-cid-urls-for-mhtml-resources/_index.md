---
title: تصدير عناوين URL لـ Cid للحصول على موارد Mhtml
linktitle: تصدير عناوين URL لـ Cid للحصول على موارد Mhtml
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير عناوين URL الخاصة بـ CID لموارد MHTML عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لتصدير عناوين URL الخاصة بـ CID لموارد MHTML باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير عناوين URL الخاصة بـ CID لموارد MHTML عند حفظ مستند بتنسيق MHTML.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل المستند للتصدير. استخدم الكود التالي لتحميل المستند من دليل محدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 يقوم هذا الرمز بإنشاء مثيل لـ`Document` عن طريق تحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ HTML

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير عناوين URL الخاصة بـ CID لموارد MHTML. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` مع ضبط تنسيق الحفظ على MHTML. كما أنه يتيح تصدير عناوين URL الخاصة بـ CID لموارد MHTML عن طريق الإعداد`ExportCidUrlsForMhtmlResources` ل`true`.

## الخطوة 4: تحويل وحفظ المستند إلى MHTML

وأخيرًا، سنقوم بتحويل المستند إلى MHTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى MHTML وحفظه في ملف يحتوي على عناوين URL الخاصة بـ CID لموارد MHTML المصدرة.

### مثال على التعليمات البرمجية المصدر لتصدير عناوين URL لـ Cid لموارد Mhtml باستخدام Aspose.Words لـ .NET

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

لقد تعلمت الآن كيفية تصدير عناوين URL الخاصة بـ CID لموارد MHTML عند حفظ مستند بتنسيق MHTML باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إدارة عناوين URL الخاصة بـ CID في مستندات MHTML المصدرة.

