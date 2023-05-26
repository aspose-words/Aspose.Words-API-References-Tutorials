---
title: احصل على نقاط حدود الشكل الفعلي
linktitle: احصل على نقاط حدود الشكل الفعلي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استرداد الحدود الفعلية للشكل بالنقاط (وحدة القياس) في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/get-actual-shape-bounds-points/
---

يشرح هذا البرنامج التعليمي كيفية استرداد الحدود الفعلية للشكل بالنقاط (وحدة القياس) في مستند Word باستخدام Aspose.Words for .NET. تمثل الحدود حجم وموضع الشكل داخل المستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل شكل صورة
 استخدم ال`InsertImage` طريقة`DocumentBuilder` كائن لإدراج شكل صورة في المستند. قم بتوفير المسار لملف الصورة كمعامل.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## الخطوة 3: استرجع نقاط حدود الشكل الفعلية
 الوصول إلى الأشكال`ShapeRenderer` باستخدام`GetShapeRenderer`طريقة. ثم استرجع الحدود الفعلية للشكل بالنقاط باستخدام`BoundsInPoints` ملكية.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### مثال على شفرة المصدر للحصول على نقاط حدود الشكل الفعلية باستخدام Aspose.Words for .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

هذا كل شيء! لقد نجحت في استرداد الحدود الفعلية للشكل بالنقاط في مستند Word باستخدام Aspose.Words for .NET.