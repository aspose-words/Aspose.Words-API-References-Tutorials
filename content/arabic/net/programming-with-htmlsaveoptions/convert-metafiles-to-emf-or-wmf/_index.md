---
title: تحويل ملفات التعريف إلى Emf أو Wmf
linktitle: تحويل ملفات التعريف إلى Emf أو Wmf
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحويل ملفات التعريف إلى تنسيقات EMF أو WMF عند تحويل مستند إلى HTML باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتحويل ملفات التعريف إلى تنسيق EMF أو WMF باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تحويل الصور بتنسيق ملف تعريف إلى تنسيقات أكثر توافقًا مثل EMF أو WMF عند تحويل مستند إلى HTML.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إدراج صورة في المستند

في هذه الخطوة، سنقوم بإدراج صورة في المستند المراد تحويله. استخدم التعليمة البرمجية التالية لإدراج صورة من مصدر بيانات باستخدام علامة HTML:

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
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 يقوم هذا الرمز بإنشاء مثيل لـ`Document`و`DocumentBuilder` لبناء الوثيقة. يقوم بإدراج`<img>` ضع علامة في المستند باستخدام صورة مشفرة باستخدام Base64.

## الخطوة 3: قم بتعيين خيارات حفظ HTML

سنقوم الآن بتعيين خيارات حفظ HTML، بما في ذلك تنسيق ملف التعريف الذي سيتم استخدامه للصور. استخدم الكود التالي:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions` ومجموعات`MetafileFormat` ل`HtmlMetafileFormat.EmfOrWmf` لتحديد أنه يجب تحويل ملفات التعريف إلى تنسيق EMF أو WMF عند التحويل إلى HTML.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML المحددة مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML وحفظه في ملف يحتوي على ملفات التعريف المحولة بتنسيق EMF أو WMF اعتمادًا على مجموعة خيارات الحفظ.

### مثال على التعليمات البرمجية المصدر لتحويل ملفات التعريف إلى Emf أو Wmf باستخدام Aspose.Words لـ .NET

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
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تحويل ملفات التعريف إلى تنسيقات EMF أو WMF عند تحويل مستند إلى HTML باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إدارة ملفات التعريف في مستندات HTML المحولة.