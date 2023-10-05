---
title: تحديث الرسم الفني الذكي
linktitle: تحديث الرسم الفني الذكي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديث رسم Smart Art في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/update-smart-art-drawing/
---

يشرح هذا البرنامج التعليمي كيفية تحديث رسم Smart Art في مستند Word باستخدام Aspose.Words لـ .NET. من خلال تكرار الأشكال الموجودة في المستند والتحقق مما إذا كانت تحتوي على Smart Art، يمكنك تحديث رسم Smart Art ليعكس أي تغييرات تم إجراؤها على بياناته.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
قم بتحميل مستند Word الذي يحتوي على رسم Smart Art باستخدام الملف`Document` منشئ الطبقة.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## الخطوة 3: تحديث الرسم الفني الذكي
 قم بالتكرار عبر الأشكال الموجودة في المستند باستخدام`GetChildNodes` الطريقة مع`NodeType.Shape` معامل. تحقق مما إذا كان كل شكل يحتوي على Smart Art باستخدام`HasSmartArt` الملكية، وإذا كان صحيحا، استدعاء`UpdateSmartArtDrawing` طريقة لتحديث رسم Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### مثال على التعليمات البرمجية المصدر لتحديث Smart Art Painting باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

هذا كل شيء! لقد قمت بنجاح بتحديث رسم Smart Art في مستند Word الخاص بك باستخدام Aspose.Words لـ .NET.