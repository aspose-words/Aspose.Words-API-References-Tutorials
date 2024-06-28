---
title: إدراج الشكل
linktitle: إدراج الشكل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الأشكال في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/insert-shape/
---

يشرح هذا البرنامج التعليمي كيفية إدراج الأشكال في مستند Word باستخدام Aspose.Words لـ .NET. يمكن استخدام الأشكال لتحسين المظهر المرئي وتخطيط مستنداتك.

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

## الخطوة 3: إدراج الأشكال
 استخدم ال`InsertShape` طريقة`DocumentBuilder`كائن لإدراج الأشكال في المستند. حدد نوع الشكل والمواضع الأفقية والرأسية النسبية وأبعاد الصفحة والحجم ونوع التغليف. يمكنك أيضًا ضبط زاوية دوران الأشكال إذا رغبت في ذلك.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## الخطوة 4: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.InsertShape.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### مثال على التعليمات البرمجية المصدر لإدراج الشكل باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

هذا كل شيء! لقد نجحت في إدراج الأشكال في مستند Word الخاص بك باستخدام Aspose.Words لـ .NET.