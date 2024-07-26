---
title: نسبة العرض إلى الارتفاع مقفلة
linktitle: نسبة العرض إلى الارتفاع مقفلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تأمين أو إلغاء قفل نسبة العرض إلى الارتفاع لشكل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/aspect-ratio-locked/
---

يشرح هذا البرنامج التعليمي كيفية قفل أو إلغاء قفل نسبة العرض إلى الارتفاع لشكل في مستند Word باستخدام Aspose.Words for .NET. من خلال قفل نسبة العرض إلى الارتفاع، يمكنك الحفاظ على النسب الأصلية للشكل عند تغيير حجمه.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وDocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج شكل صورة
 استخدم ال`InsertImage` طريقة`DocumentBuilder` كائن لإدراج شكل صورة في المستند. توفير المسار إلى ملف الصورة كمعلمة.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## الخطوة 4: قفل أو فتح نسبة العرض إلى الارتفاع
 تعيين`AspectRatioLocked` خاصية الشكل ل`true` أو`false` لقفل أو إلغاء قفل نسبة العرض إلى الارتفاع، على التوالي.

```csharp
shape.AspectRatioLocked = false; // فتح نسبة العرض إلى الارتفاع
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### مثال على التعليمات البرمجية المصدر لنسبة العرض إلى الارتفاع المقفلة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

هذا كل شيء! لقد نجحت في تأمين أو إلغاء تأمين نسبة العرض إلى الارتفاع لشكل في مستند Word الخاص بك باستخدام Aspose.Words for .NET.