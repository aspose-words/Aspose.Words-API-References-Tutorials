---
title: تصدير حقل نموذج إدخال النص كنص
linktitle: تصدير حقل نموذج إدخال النص كنص
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لتصدير حقول نموذج إدخال النص كنص عادي باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتصدير حقول نموذج إدخال النص كنص عادي باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير حقول نموذج إدخال النص كنص مقروء ، بدلاً من تصديرها كعناصر إدخال HTML.

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

سنقوم الآن بتكوين خيارات حفظ HTML لتصدير حقول نموذج إدخال النص كنص عادي. استخدم الكود التالي:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// يجب أن يكون المجلد المحدد موجودًا وأن يكون فارغًا.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 هذا الرمز ينشئ مثيل`HtmlSaveOptions`وتعيين`ExportTextInputFormFieldAsText` الخيار ل`true`لتصدير حقول نموذج إدخال النص كنص عادي. علاوة على ذلك ، فإنه يحدد المجلد حيث سيتم حفظ الصور المستخرجة.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

أخيرًا ، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

يحول هذا الرمز المستند إلى HTML عن طريق تصدير حقول نموذج إدخال النص كنص عادي ، ويحفظ ملف HTML الذي تم تصديره إلى الدليل المحدد.

### مثال على شفرة المصدر لحقل نموذج إدخال النص على هيئة نص باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// يجب أن يكون المجلد المحدد موجودًا ويجب أن يكون فارغًا.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// قم بتعيين خيار لتصدير حقول النموذج كنص عادي ، وليس كعناصر إدخال HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.