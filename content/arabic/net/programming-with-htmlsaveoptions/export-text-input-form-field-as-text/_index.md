---
title: تصدير حقل نموذج إدخال النص كنص
linktitle: تصدير حقل نموذج إدخال النص كنص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير حقول نموذج إدخال النص كنص عادي باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتصدير حقول نموذج إدخال النص كنص عادي باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تصدير حقول نموذج إدخال النص كنص قابل للقراءة، بدلاً من تصديرها كعناصر إدخال HTML.

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

 يقوم هذا الرمز بإنشاء مثيل لـ`HtmlSaveOptions`ويحدد`ExportTextInputFormFieldAsText` خيار ل`true` لتصدير حقول نموذج إدخال النص كنص عادي. علاوة على ذلك، فإنه يحدد المجلد الذي سيتم حفظ الصور المستخرجة فيه.

## الخطوة 4: تحويل وحفظ المستند إلى HTML

وأخيرًا، سنقوم بتحويل المستند إلى HTML باستخدام خيارات حفظ HTML التي تم تكوينها مسبقًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

يقوم هذا الرمز بتحويل المستند إلى HTML عن طريق تصدير حقول نموذج إدخال النص كنص عادي، ويحفظ ملف HTML الذي تم تصديره إلى الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لتصدير حقل نموذج إدخال النص كنص باستخدام Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// يجب أن يكون المجلد المحدد موجودًا ويجب أن يكون فارغًا.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// قم بتعيين خيار لتصدير حقول النموذج كنص عادي، وليس كعناصر إدخال HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات في ملف`dataDir` عامل.