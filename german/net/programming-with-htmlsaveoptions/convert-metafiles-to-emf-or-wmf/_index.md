---
title: تحويل ملفات التعريف إلى Emf أو Wmf
linktitle: تحويل ملفات التعريف إلى Emf أو Wmf
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتحويل ملفات التعريف إلى تنسيقات EMF أو WMF عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتحويل ملفات التعريف إلى تنسيق EMF أو WMF باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تحويل الصور بتنسيق ملف تعريف إلى تنسيقات أكثر توافقًا مثل EMF أو WMF عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إدراج صورة في المستند

في هذه الخطوة ، سنقوم بإدراج صورة في المستند المراد تحويله. استخدم الكود التالي لإدراج صورة من مصدر بيانات باستخدام علامة HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6 + ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 هذا الرمز ينشئ مثيل`Document` و`DocumentBuilder` لبناء الوثيقة. يقوم بإدراج ملف`<img>` علامة في المستند مع صورة مشفرة base64.

## الخطوة 3: تعيين خيارات حفظ HTML

سنقوم الآن بتعيين خيارات حفظ HTML ، بما في ذلك تنسيق ملف التعريف لاستخدامه مع الصور. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions` ومجموعات`MetafileFormat` ل`HtmlMetafileFormat.EmfOrWmf` لتحديد أن ملفات التعريف يجب تحويلها إلى تنسيق EMF أو WMF عند التحويل إلى HTML.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML المحددة مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML ويحفظه في ملف به ملفات التعريف المحولة بتنسيق EMF أو WMF اعتمادًا على مجموعة خيارات الحفظ.

### مثال على شفرة المصدر لتحويل ملفات التعريف إلى Emf أو Wmf باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6 + ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تحويل ملفات التعريف إلى تنسيقات EMF أو WMF عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إدارة ملفات التعريف في مستندات HTML المحولة.