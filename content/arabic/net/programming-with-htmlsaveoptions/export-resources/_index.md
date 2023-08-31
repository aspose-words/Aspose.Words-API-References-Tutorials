---
title: تصدير الموارد
linktitle: تصدير الموارد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير موارد المستند عند حفظه بتنسيق HTML باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-resources/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتصدير موارد المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير الموارد، مثل الخطوط، كملفات خارجية عند حفظ مستند بتنسيق HTML.

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

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير موارد المستند. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` ويضبط الخيارات التالية:

- `CssStyleSheetType` تم ضبطه على`CssStyleSheetType.External`لتصدير ورقة أنماط CSS إلى ملف خارجي.
- `ExportFontResources` تم ضبطه على`true` لتصدير موارد الخطوط.
- `ResourceFolder` يحدد الدليل الوجهة حيث سيتم حفظ الموارد.
- `ResourceFolderAlias` يحدد الاسم المستعار لعنوان URL الذي سيتم استخدامه للوصول إلى الموارد.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML وحفظ الموارد في الدليل المحدد، باستخدام الاسم المستعار لعنوان URL المحدد.

### مثال على التعليمات البرمجية المصدر لتصدير الموارد باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.