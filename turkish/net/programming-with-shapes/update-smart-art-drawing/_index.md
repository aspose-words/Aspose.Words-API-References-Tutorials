---
title: تحديث الرسم الفني الذكي
linktitle: تحديث الرسم الفني الذكي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديث الرسم الفني الذكي في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/update-smart-art-drawing/
---

يشرح هذا البرنامج التعليمي كيفية تحديث الرسم الفني الذكي في مستند Word باستخدام Aspose.Words for .NET. من خلال التكرار خلال الأشكال في المستند والتحقق مما إذا كانت تحتوي على Smart Art ، يمكنك تحديث رسم Smart Art ليعكس أي تغييرات تم إجراؤها على بياناته.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
 قم بتحميل مستند Word الذي يحتوي على رسم Smart Art باستخدام ملف`Document` منشئ الطبقة.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## الخطوة 3: تحديث الرسم الفني الذكي
 كرر عبر الأشكال الموجودة في المستند باستخدام تنسيق`GetChildNodes` الطريقة مع`NodeType.Shape` معامل. تحقق مما إذا كان كل شكل يحتوي على Smart Art باستخدام ملف`HasSmartArt` الخاصية ، وإذا كان هذا صحيحًا ، فاتصل بـ`UpdateSmartArtDrawing` طريقة لتحديث الرسم الفني الذكي.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### مثال على الكود المصدري لتحديث الرسم الفني الذكي باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

هذا كل شيء! لقد نجحت في تحديث رسم Smart Art في مستند Word باستخدام Aspose.Words for .NET.