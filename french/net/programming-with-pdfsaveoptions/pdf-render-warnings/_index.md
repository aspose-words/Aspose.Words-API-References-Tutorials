---
title: تحذيرات تقديم ملف PDF
linktitle: تحذيرات تقديم ملف PDF
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة للتعامل مع تحذيرات عرض PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة تحذيرات عرض PDF مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية التعامل مع تحذيرات العرض عند التحويل إلى PDF.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "WMF with image.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## الخطوة 3: تكوين خيارات الحفظ كملف PDF مع تحذيرات التقديم

للتعامل مع تحذيرات التجسيد عند التحويل إلى PDF ، نحتاج إلى تكوين ملف`MetafileRenderingOptions` لتحديد كيفية عرض ملفات التعريف. نستخدم أيضًا ملف`HandleDocumentWarnings` خيار للتعامل مع التحذيرات التي تم إنشاؤها عند حفظ المستند.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## الخطوة 4: احفظ المستند بصيغة PDF مع تحذيرات التقديم

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## الخطوة 5: التعامل مع تحذيرات العرض

يمكن استرجاع تحذيرات التجسيد التي تم إنشاؤها عند حفظ المستند باستخدام معالج التحذير المخصص. في هذا المثال ، نقوم ببساطة بطباعة وصف كل تحذير.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

هذا كل شئ ! لقد نجحت في معالجة تحذيرات العرض عند تحويل مستند

  إلى PDF باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لتحذيرات عرض PDF باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// إذا تعذر على Aspose.Words عرض بعض سجلات ملف التعريف بشكل صحيح
	// إلى الرسومات المتجهة ، ثم يقوم Aspose.Words بجعل ملف التعريف هذا إلى صورة نقطية.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// أثناء حفظ الملف بنجاح ، يتم هنا تجميع تحذيرات العرض التي حدثت أثناء الحفظ.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
