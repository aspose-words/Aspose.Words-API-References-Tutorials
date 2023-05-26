---
title: تصدير الموارد
linktitle: تصدير الموارد
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتصدير موارد المستندات عند الحفظ بتنسيق HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-resources/
---

في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # لتصدير موارد المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير الموارد ، مثل الخطوط ، كملفات خارجية عند حفظ مستند بتنسيق HTML.

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

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير موارد المستند. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources "
};
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions` وتعيين الخيارات التالية:

- `CssStyleSheetType` تم تعيينه على`CssStyleSheetType.External`لتصدير ورقة أنماط CSS إلى ملف خارجي.
- `ExportFontResources` تم تعيينه على`true` لتصدير موارد الخط.
- `ResourceFolder` يحدد الدليل الوجهة حيث سيتم حفظ الموارد.
- `ResourceFolderAlias` يحدد عنوان URL المستعار الذي سيتم استخدامه للوصول إلى الموارد.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML ويحفظ الموارد في الدليل المحدد ، باستخدام الاسم المستعار لعنوان URL المحدد.

### مثال على شفرة المصدر لتصدير الموارد باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources "
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.