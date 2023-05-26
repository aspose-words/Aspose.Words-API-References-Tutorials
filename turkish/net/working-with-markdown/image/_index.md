---
title: صورة
linktitle: صورة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الصورة وتخصيصها باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /tr/net/working-with-markdown/image/
---

في هذا المثال ، سنشرح كيفية استخدام ميزة الصورة مع Aspose.Words for .NET. تسمح لك الصور بإدراج الرسوم التوضيحية والرسومات في المستند.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة الثانية: إدخال صورة

 يمكننا إدراج صورة باستخدام ملف`Shape` فئة وتحديد نوع الصورة هنا`ShapeType.Image` قمنا أيضًا بتعيين نوع التفاف الصورة على`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## الخطوة 3: تخصيص الصورة

 نقوم بتخصيص الصورة من خلال تحديد مسارها الكامل ، على سبيل المثال`"/attachment/1456/pic001.png"`وإضافة عنوان للصورة.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### مثال على شفرة المصدر للصور باستخدام Aspose.Words for .NET

```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// إدراج صورة.
	Shape shape = new Shape(builder.Document, ShapeType.Image);
	shape.WrapType = WrapType.Inline;
	shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
	shape.ImageData.Title = "title";
	builder.InsertNode(shape);
            
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الصور مع Aspose.Words for .NET.

