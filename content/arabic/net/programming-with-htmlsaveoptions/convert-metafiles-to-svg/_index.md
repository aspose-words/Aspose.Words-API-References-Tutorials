---
title: تحويل ملفات التعريف إلى Svg
linktitle: تحويل ملفات التعريف إلى Svg
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحويل ملفات التعريف إلى تنسيق SVG عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتحويل ملفات التعريف إلى تنسيق SVG باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تحويل ملفات التعريف إلى تنسيق SVG عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إدراج صورة SVG في المستند

في هذه الخطوة، سنقوم بإدراج صورة SVG في المستند المراد تحويله. استخدم التعليمة البرمجية التالية لإدراج صورة SVG باستخدام علامة HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 يقوم هذا الرمز بإنشاء مثيل لـ`Document`و`DocumentBuilder` لبناء الوثيقة. يقوم بإدراج أ`<svg>` العلامة التي تحتوي على أ`<polygon>` عنصر ذو سمات لتحديد شكل ونمط صورة SVG.

## الخطوة 3: قم بتعيين خيارات حفظ HTML

سنقوم الآن بتعيين خيارات حفظ HTML، مع تحديد أنه يجب تحويل ملفات التعريف إلى تنسيق SVG. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` ومجموعات`MetafileFormat` ل`HtmlMetafileFormat.Svg` لتحديد أنه يجب تحويل ملفات التعريف إلى تنسيق SVG عند التحويل إلى HTML.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML المحددة مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML وحفظه في ملف به ملفات التعريف المحولة إلى SVG.

### مثال على التعليمات البرمجية المصدر لتحويل ملفات التعريف إلى Svg باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
