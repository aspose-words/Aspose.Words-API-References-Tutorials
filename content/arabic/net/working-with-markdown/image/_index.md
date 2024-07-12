---
title: صورة
linktitle: صورة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الصورة وتخصيصها باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/image/
---

في هذا المثال، سنشرح كيفية استخدام ميزة الصورة مع Aspose.Words for .NET. تسمح لك الصور بإدراج الرسوم التوضيحية والرسومات في المستند.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إدراج صورة

 يمكننا إدراج صورة باستخدام`Shape` فئة وتحديد نوع الصورة، هنا`ShapeType.Image` . قمنا أيضًا بتعيين نوع التفاف الصورة على`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## الخطوة 3: تخصيص الصورة

 نقوم بتخصيص الصورة من خلال تحديد مسارها الكامل، على سبيل المثال`"/attachment/1456/pic001.png"`وإضافة عنوان للصورة.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### مثال على التعليمات البرمجية المصدر للصور باستخدام Aspose.Words لـ .NET

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

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الصور مع Aspose.Words لـ .NET.


### الأسئلة الشائعة

#### س: كيف يمكنني إدراج صورة من ملف محلي في Aspose.Words؟

 ج: لإدراج صورة من ملف محلي في Aspose.Words، يمكنك استخدام الملف`Shape` الطبقة و`InsertImage` طريقة.

#### س: هل يمكنني إدراج صورة من عنوان URL في Aspose.Words؟

 ج: نعم، يمكنك إدراج صورة من عنوان URL في Aspose.Words. يمكنك استخدام نفس الشيء`InsertImage`الطريقة وحدد عنوان URL للصورة بدلاً من مسار الملف المحلي.

#### س: كيف يمكنني تغيير حجم الصورة في Aspose.Words؟

 ج: لتغيير حجم الصورة في Aspose.Words، يمكنك استخدام الملف`Width`و`Height` خصائص`Shape` هدف.

#### س: هل يمكنني تطبيق المرشحات على الصور في Aspose.Words؟

 ج: نعم، يمكنك تطبيق المرشحات على الصور في Aspose.Words. على سبيل المثال، يمكنك تطبيق مرشح التمويه على صورة ما باستخدام`ApplyGaussianBlur` طريقة`Shape` هدف.

#### س: كيف يمكنني استبدال صورة بأخرى في Aspose.Words؟

 ج: لاستبدال صورة بأخرى في Aspose.Words، يمكنك استخدام`Replace` طريقة`Shape` فصل. تأخذ هذه الطريقة كمعلمة`Shape` كائن الصورة المراد استبداله و`Shape` كائن الصورة الجديدة.