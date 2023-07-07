---
title: مراجعة الشكل
linktitle: مراجعة الشكل
second_title: Aspose.Words لمراجع .NET API
description: راجع الأشكال في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/shape-revision/
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

## الخطوة 2: تتبع المراجعات وأضف شكلًا آخر

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

//قم بإدراج شكل مضمن بدون تعقب المراجعات.
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

// يحتوي المستند على شكل واحد تم نقله ، لكن مراجعات نقل الشكل سيكون لها مثيلين لهذا الشكل.
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إجراء مراجعات على الأشكال في مستند Word باستخدام Aspose.Words for .NET. باتباع خطوات إنشاء المستند ، وتمكين تتبع المراجعة ، والتحقق من المراجعات المرتبطة بكل شكل ، والتحقق من المراجعات لنقل الأشكال ، تمكنا من إدارة المراجعات بنجاح. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية للعمل مع المراجعات والنماذج في مستندات Word.

### التعليمات

#### س: كيف يمكنني إنشاء مستند جديد وإضافة أشكال في Aspose.Words for .NET؟

ج: لإنشاء مستند جديد وإضافة أشكال في Aspose.Words for .NET ، يمكنك استخدام الكود التالي. نضيف هنا شكلين ، مكعب وشمس ، إلى القسم الأول من المستند:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### س: كيف يمكنني تمكين تتبع المراجعة في Aspose.Words for .NET؟

 ج: لتمكين تتبع المراجعة في Aspose.Words for .NET ، يمكنك استخدام`StartTrackRevisions` طريقة`Document` هدف. تأخذ هذه الطريقة اسم مؤلف المراجعات كمعامل:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### س: كيف يمكنني التحقق من المراجعات المرتبطة بكل شكل في مستند Aspose.Words for .NET؟

ج: للتحقق من المراجعات المرتبطة بكل شكل في مستند Aspose.Words for .NET ، يمكنك الحصول على مجموعة أشكال المستند باستخدام`GetChildNodes` الطريقة مع`NodeType.Shape` نوع العقدة. ثم يمكنك الوصول إلى كل شكل`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` ، و`IsMoveToRevision` لتحديد نوع المراجعة المرتبطة بالشكل:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### س: كيف يمكنني التحقق من مراجعات الإزاحة للأشكال في مستند Aspose.Words لمستند .NET؟

 ج: للتحقق من مراجعات إزاحة الشكل في مستند Aspose.Words for .NET ، يمكنك تحميل مستند موجود يحتوي على مراجعات إزاحة الشكل. ثم يمكنك الوصول إلى كل شكل`IsMoveFromRevision` و`IsMoveToRevision` لتحديد ما إذا كان يتم نقله ، وإذا كان الأمر كذلك ، فمن أين وإلى أين:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```