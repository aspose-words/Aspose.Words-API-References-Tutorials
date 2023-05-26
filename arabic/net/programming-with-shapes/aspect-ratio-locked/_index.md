---
title: نسبة العرض إلى الارتفاع مقفلة
linktitle: نسبة العرض إلى الارتفاع مقفلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية قفل أو إلغاء قفل نسبة العرض إلى الارتفاع لشكل ما في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/aspect-ratio-locked/
---

يشرح هذا البرنامج التعليمي كيفية قفل أو إلغاء قفل نسبة العرض إلى الارتفاع لشكل ما في مستند Word باستخدام Aspose.Words for .NET. بقفل نسبة العرض إلى الارتفاع ، يمكنك الحفاظ على النسب الأصلية للشكل عند تغيير حجمه.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل شكل صورة
 استخدم ال`InsertImage` طريقة`DocumentBuilder` كائن لإدراج شكل صورة في المستند. قم بتوفير المسار لملف الصورة كمعامل.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## الخطوة 4: قفل أو فتح نسبة العرض إلى الارتفاع
 تعيين`AspectRatioLocked` خاصية الشكل ل`true` أو`false`لقفل أو إلغاء قفل نسبة العرض إلى الارتفاع ، على التوالي.

```csharp
shape.AspectRatioLocked = false; // افتح نسبة العرض إلى الارتفاع
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### مثال على شفرة المصدر لـ Aspect Ratio Locked باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

هذا كل شيء! لقد نجحت في تأمين أو إلغاء قفل نسبة العرض إلى الارتفاع لشكل ما في مستند Word باستخدام Aspose.Words for .NET.