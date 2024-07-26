---
title: احصل على نقاط حدود الشكل الفعلية
linktitle: احصل على نقاط حدود الشكل الفعلية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد الحدود الفعلية للشكل بالنقاط (وحدة القياس) في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/get-actual-shape-bounds-points/
---

يشرح هذا البرنامج التعليمي كيفية استرداد الحدود الفعلية للشكل بالنقاط (وحدة القياس) في مستند Word باستخدام Aspose.Words for .NET. تمثل الحدود حجم الشكل وموضعه داخل المستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إنشاء مستند جديد وDocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج شكل الصورة
 استخدم ال`InsertImage` طريقة`DocumentBuilder` كائن لإدراج شكل صورة في المستند. توفير المسار إلى ملف الصورة كمعلمة.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## الخطوة 3: استرداد نقاط حدود الشكل الفعلية
 الوصول إلى الشكل`ShapeRenderer` باستخدام`GetShapeRenderer` طريقة. ثم قم باسترداد الحدود الفعلية للشكل بالنقاط باستخدام`BoundsInPoints` ملكية.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### مثال على التعليمات البرمجية المصدر للحصول على نقاط حدود الشكل الفعلية باستخدام Aspose.Words لـ .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

هذا كل شيء! لقد نجحت في استرداد الحدود الفعلية للشكل بالنقاط في مستند Word الخاص بك باستخدام Aspose.Words for .NET.