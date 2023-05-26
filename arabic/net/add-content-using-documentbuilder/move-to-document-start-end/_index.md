---
title: الانتقال إلى المستند بداية النهاية
linktitle: الانتقال إلى المستند بداية النهاية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET للانتقال إلى بداية المستند ونهايته في مستندات Word باستخدام هذا الدليل التفصيلي.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-document-start-end/
---

في هذا المثال ، سوف نستكشف ميزة Move To Document Start / End في Aspose.Words for .NET. Aspose.Words مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word وتعديلها وتحويلها برمجيًا. تتيح لنا ميزة Move To Document Start / End إمكانية التنقل إلى بداية المستند أو نهايته باستخدام فئة DocumentBuilder.

## شرح شفرة المصدر خطوة بخطوة

دعنا ننتقل إلى التعليمات البرمجية المصدر خطوة بخطوة لفهم كيفية استخدام ميزة Move To Document Start / End باستخدام Aspose.Words for .NET.


## الخطوة 1: تهيئة مستند إنشاء المستندات

بعد ذلك ، قم بتهيئة كائنات Document و DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: الانتقال إلى بداية المستند

لنقل موضع المؤشر إلى بداية المستند ، استخدم طريقة MoveToDocumentStart لفئة DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## الخطوة 3: الانتقال إلى نهاية المستند

لتحريك موضع المؤشر إلى نهاية المستند ، استخدم طريقة MoveToDocumentEnd لفئة DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## الخطوة 4: إخراج موضع المؤشر

يمكنك إخراج موضع المؤشر باستخدام Console.WriteLine أو أي طريقة أخرى مرغوبة. على سبيل المثال:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### مثال على شفرة المصدر لـ Move To Document Start / End باستخدام Aspose.Words for .NET

```csharp
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// انقل موضع المؤشر إلى بداية المستند.
	builder.MoveToDocumentStart();
	Console.WriteLine("\nThis is the beginning of the document.");

	// انقل موضع المؤشر إلى نهاية المستند.
	builder.MoveToDocumentEnd();
	Console.WriteLine("\nThis is the end of the document.");
	
```

## خاتمة

في هذا المثال ، اكتشفنا ميزة Move To Document Start / End في Aspose.Words for .NET. تعلمنا كيفية الانتقال إلى بداية ونهاية المستند باستخدام فئة DocumentBuilder. هذه الميزة مفيدة عند العمل برمجيًا مع مستندات Word والحاجة إلى معالجة المحتوى أو إدراجه في مواضع محددة داخل المستند.