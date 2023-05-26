---
title: أضف شكل المجموعة
linktitle: أضف شكل المجموعة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة شكل مجموعة بأشكال متعددة إلى مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-group-shape/
---

يشرح هذا البرنامج التعليمي كيفية إضافة شكل مجموعة يحتوي على أشكال متعددة إلى مستند Word باستخدام Aspose.Words for .NET. تسمح لك أشكال المجموعة بدمج أشكال متعددة ومعالجتها ككيان واحد.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وشكل جماعي
 قم بإنشاء مثيل جديد لملف`Document` فئة و`GroupShape` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## الخطوة 3: إنشاء وإضافة أشكال إلى GroupShape
 قم بإنشاء أشكال فردية مثل`accentBorderShape` و`actionButtonShape` باستخدام`Shape` فصل. تخصيص خصائصهم حسب الرغبة. إلحاق هذه الأشكال بملف`groupShape` هدف.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## الخطوة 4: تعيين الأبعاد لشكل المجموعة
 قم بتعيين العرض والارتفاع وحجم التنسيق لملف`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## الخطوة 5: أدخل GroupShape في المستند
 إنشاء`DocumentBuilder` الكائن وإدراج`groupShape` في المستند باستخدام ملف`InsertNode` طريقة.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save`طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### مثال على شفرة المصدر لإضافة شكل المجموعة باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

هذا كل شيء! لقد نجحت في إضافة شكل مجموعة يحتوي على أشكال متعددة إلى مستند Word الخاص بك باستخدام Aspose.W