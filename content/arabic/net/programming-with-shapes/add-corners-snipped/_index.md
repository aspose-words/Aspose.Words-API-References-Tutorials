---
title: إضافة زوايا مقطوعة
linktitle: إضافة زوايا مقطوعة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة شكل بزوايا مقصوصة إلى مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/add-corners-snipped/
---

 يشرح هذا البرنامج التعليمي كيفية إضافة شكل بزوايا مقصوصة إلى مستند Word باستخدام Aspose.Words for .NET. يمكن تخصيص شكل الزوايا المقطوعة وإدراجه باستخدام`InsertShape` طريقة.

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
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder`كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل شكل الزوايا المقطوعة
 استخدم ال`InsertShape` طريقة`DocumentBuilder` كائن لإدراج شكل مع قص الزوايا. حدد نوع الشكل (في هذه الحالة،`ShapeType.TopCornersSnipped`) وتوفير الحجم المطلوب للشكل.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## الخطوة 4: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### مثال على التعليمات البرمجية المصدر لـ Add Corners Snipped باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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

هذا كل شيء! لقد نجحت في إضافة شكل مقطوع من الزوايا إلى مستند Word الخاص بك باستخدام Aspose.Words for .NET.