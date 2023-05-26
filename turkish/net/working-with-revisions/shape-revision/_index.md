---
title: مراجعة الشكل
linktitle: مراجعة الشكل
second_title: Aspose.Words لمراجع .NET API
description: راجع الأشكال في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-revisions/shape-revision/
---

في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية إجراء مراجعات للأشكال في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: إنشاء المستند وإضافة الأشكال

تتمثل الخطوة الأولى في إنشاء مستند جديد وإضافة أشكال.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## الخطوة 2: تتبع المراجعات وإضافة شكل آخر

سنقوم بتشغيل تتبع المراجعة وإضافة شكل آخر.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## الخطوة 3: احصل على مجموعة الأشكال وتحقق من المراجعات

سنحصل على مجموعة الأشكال من المستند ونتحقق من المراجعات المرتبطة بكل شكل.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## الخطوة 4: التحقق من تنقيحات نقل الشكل

سنقوم بتحميل مستند موجود يحتوي على مراجعات إزاحة الشكل والتحقق من المراجعات المرتبطة.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### مثال على شفرة المصدر لـ Shape Revision باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لإجراء مراجعات على الأشكال في مستند باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document();

	// قم بإدراج شكل مضمن بدون تعقب المراجعات.
	Assert.False(doc.TrackRevisions);
	Shape shape = new Shape(doc, ShapeType.Cube);
	shape.WrapType = WrapType.Inline;
	shape.Width = 100.0;
	shape.Height = 100.0;
	doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

	// بدء تعقب المراجعات ثم قم بإدراج شكل آخر.
	doc.StartTrackRevisions("John Doe");
	shape = new Shape(doc, ShapeType.Sun);
	shape.WrapType = WrapType.Inline;
	shape.Width = 100.0;
	shape.Height = 100.0;
	doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

	// احصل على مجموعة أشكال المستند التي تتضمن الشكلين اللذين أضفناهما فقط.
	List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
	Assert.AreEqual(2, shapes.Count);

	// قم بإزالة الشكل الأول.
	shapes[0].Remove();

	// نظرًا لأننا أزلنا هذا الشكل أثناء تعقب التغييرات ، فإن الشكل يعد بمثابة مراجعة حذف.
	Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
	Assert.True(shapes[0].IsDeleteRevision);

	// وقمنا بإدخال شكل آخر أثناء تتبع التغييرات ، بحيث يتم احتساب هذا الشكل كمراجعة إدراج.
	Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
	Assert.True(shapes[1].IsInsertRevision);

	//يحتوي المستند على شكل واحد تم نقله ، لكن مراجعات نقل الشكل سيكون لها مثيلين لهذا الشكل.
	// سيكون أحدهما الشكل في وجهة وصوله والآخر سيكون الشكل في موقعه الأصلي.
	doc = new Document(MyDir + "Revision shape.docx");
	
	shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
	Assert.AreEqual(2, shapes.Count);

	// هذه هي الخطوة إلى المراجعة ، وكذلك الشكل في وجهة وصولها.
	Assert.False(shapes[0].IsMoveFromRevision);
	Assert.True(shapes[0].IsMoveToRevision);

	// هذا هو الانتقال من المراجعة ، وهو الشكل الموجود في موقعه الأصلي.
	Assert.True(shapes[1].IsMoveFromRevision);
	Assert.False(shapes[1].IsMoveToRevision);
            
```

