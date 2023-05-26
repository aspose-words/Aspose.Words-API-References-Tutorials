---
title: أضف علامة مائية نصية مع خيارات محددة
linktitle: أضف علامة مائية نصية مع خيارات محددة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /zh/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية إضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words for .NET. العلامة المائية النصية هي نص متراكب على مستند للإشارة إلى أنه مسودة وسري وما إلى ذلك.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة الثانية: تحميل المستند

سنقوم بتحميل مستند موجود باستخدام مسار المستند.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 3: أضف علامة مائية نصية بخيارات محددة

 سنقوم بإنشاء مثيل لـ`TextWatermarkOptions` فئة وتعيين الخيارات المطلوبة للعلامة المائية النصية.

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

أخيرًا ، يمكننا حفظ المستند بعلامة مائية نصية مضافة.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### مثال على شفرة المصدر لإضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words for .NET

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

تهنئة ! لقد تعلمت الآن كيفية إضافة علامة مائية نصية مع خيارات محددة باستخدام Aspose.Words for .NET.

