---
title: إضافة علامة مائية نصية مع خيارات محددة
linktitle: إضافة علامة مائية نصية مع خيارات محددة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة علامة مائية نصية بخيارات محددة باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

في هذا البرنامج التعليمي، سنرشدك إلى كيفية إضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words for .NET. العلامة المائية النصية هي نص متراكب على مستند للإشارة إلى أنه مسودة أو سري وما إلى ذلك.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة

سنقوم بتحميل مستند موجود باستخدام مسار المستند.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 3: إضافة علامة مائية نصية مع خيارات محددة

 سنقوم بإنشاء مثيل لـ`TextWatermarkOptions`فئة وضبط الخيارات المطلوبة للعلامة المائية النصية.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## الخطوة 4: احفظ المستند

أخيرًا، يمكننا حفظ المستند بالعلامة المائية النصية المضافة.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### مثال على التعليمات البرمجية المصدر لإضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

تهنئة ! لقد تعلمت الآن كيفية إضافة علامة مائية نصية بخيارات محددة باستخدام Aspose.Words for .NET.

