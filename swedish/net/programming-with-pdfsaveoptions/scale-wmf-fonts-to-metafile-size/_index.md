---
title: تغيير حجم خطوط Wmf إلى حجم ملف التعريف
linktitle: تغيير حجم خطوط Wmf إلى حجم ملف التعريف
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لضبط حجم خط WMF عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة WMF Font Scaling to Metafile Size مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تمكين أو تعطيل قياس خط WMF عند التحويل إلى PDF.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "WMF with text.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## الخطوة 3: تكوين خيارات عرض ملف التعريف

 لتمكين أو تعطيل تحجيم خط WMF إلى حجم ملف التعريف ، نحتاج إلى تكوين ملف`MetafileRenderingOptions` هدف. في هذا المثال ، نقوم بتعطيل تحجيم الخط عن طريق تعيين الامتداد`ScaleWmfFontsToMetafileSize` ملكية ل`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## الخطوة 4: تكوين خيارات حفظ كملف PDF مع خيارات عرض ملف التعريف

أخيرًا ، يمكننا تكوين خيارات الحفظ إلى PDF باستخدام خيارات عرض ملف التعريف التي تم تكوينها مسبقًا.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## الخطوة 5: احفظ المستند بصيغة PDF باستخدام خيارات عرض ملف التعريف

احفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تمكين أو تعطيل تحجيم خط WMF إلى حجم ملف التعريف عند التحويل

مستند PDF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لمقياس خطوط WMF إلى حجم ملف التعريف باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// إذا تعذر على Aspose.Words عرض بعض سجلات ملف التعريف بشكل صحيح إلى رسومات متجهة
	// ثم يعرض Aspose.Words ملف التعريف هذا إلى صورة نقطية.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
