---
title: أضف زوايا مقصوصة
linktitle: أضف زوايا مقصوصة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة شكل بزوايا مقصوصة إلى مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/add-corners-snipped/
---

 يشرح هذا البرنامج التعليمي كيفية إضافة شكل بزوايا مقصوصة إلى مستند Word باستخدام Aspose.Words for .NET. يمكن تخصيص شكل الزوايا المقطوعة وإدخالها باستخدام ملف`InsertShape` طريقة.

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

## الخطوة 3: أدخل شكل الزوايا المقصوصة
 استخدم ال`InsertShape` طريقة`DocumentBuilder` لإدراج شكل بزوايا مقصوصة. حدد نوع الشكل (في هذه الحالة ،`ShapeType.TopCornersSnipped`) وتقديم الحجم المطلوب للشكل.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## الخطوة 4: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### مثال على شفرة المصدر لـ Add Corners Snipped باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

هذا كل شيء! لقد نجحت في إضافة شكل مقطوع من الزوايا إلى مستند Word باستخدام Aspose.Words for .NET.