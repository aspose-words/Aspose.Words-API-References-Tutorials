---
title: إضافة شكل المجموعة
linktitle: إضافة شكل المجموعة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة شكل مجموعة بأشكال متعددة إلى مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/add-group-shape/
---

يشرح هذا البرنامج التعليمي كيفية إضافة شكل مجموعة يحتوي على أشكال متعددة إلى مستند Word باستخدام Aspose.Words لـ .NET. تسمح لك أشكال المجموعة بدمج أشكال متعددة ومعالجتها ككيان واحد.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وشكل المجموعة
 إنشاء مثيل جديد لـ`Document` الطبقة و`GroupShape` كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## الخطوة 3: إنشاء الأشكال وإضافتها إلى GroupShape
 إنشاء أشكال فردية مثل`accentBorderShape` و`actionButtonShape` باستخدام`Shape` فصل. تخصيص خصائصها حسب الرغبة. إلحاق هذه الأشكال إلى`groupShape` هدف.

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

## الخطوة 4: تعيين أبعاد GroupShape
 قم بتعيين العرض والارتفاع وحجم الإحداثيات للملف`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## الخطوة 5: أدخل شكل المجموعة في المستند
 إنشاء`DocumentBuilder` كائن وأدخل`groupShape` في المستند باستخدام`InsertNode` طريقة.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save`طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### مثال على التعليمات البرمجية المصدر لإضافة شكل مجموعة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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