---
title: حدود المحور في مخطط
linktitle: حدود المحور في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعيين حدود المحور في مخطط باستخدام Aspose.Words for .NET للتحكم في نطاق القيم المعروضة على المحور.
type: docs
weight: 10
url: /ar/net/programming-with-charts/bounds-of-axis/
---

يشرح هذا البرنامج التعليمي كيفية تعيين حدود المحور في مخطط باستخدام Aspose.Words for .NET. بإدراج مخطط وإضافة بيانات متسلسلة وتكوين مقياس المحور ، يمكنك تحديد الحد الأدنى والحد الأقصى لقيم المحور.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج وتكوين مخطط
 أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع الرسم البياني والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: أضف بيانات المتسلسلة
امسح أي سلسلة موجودة في المخطط وأضف بيانات سلسلة جديدة. في هذا المثال ، نضيف سلسلة ذات تسميات "العنصر 1" إلى "العنصر 5" والقيم المقابلة.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## الخطوة 5: تعيين حدود المحور
 قم بتكوين قياس المحور ص عن طريق تعيين القيم الدنيا والقصوى باستخدام`Scaling.Minimum` و`Scaling.Maximum` خصائص المحور.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### مثال على شفرة المصدر لـ Bounds Of Axis باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

هذا كل شيء! لقد نجحت في تعيين حدود المحور في الرسم البياني باستخدام Aspose.Words for .NET.

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية تعيين حدود المحور في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إدراج مخطط وتكوينه وإضافة بيانات متسلسلة وتحديد الحد الأدنى والحد الأقصى لقيم مقياس المحور. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات مع مستندات Word ، مما يسمح لك بإنشاء مخططات ديناميكية وجذابة بصريًا بسهولة.


### أسئلة وأجوبة

#### س 1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة تسمح للمطورين بالعمل مع مستندات Word برمجيًا. يوفر مجموعة واسعة من الميزات والوظائف لإنشاء مستندات Word ومعالجتها وحفظها.

#### س 2. كيف يمكنني تثبيت Aspose.Words for .NET؟
لتثبيت Aspose.Words for .NET ، يمكنك استخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س 3. هل يمكنني استخدام Aspose.Words for .NET مع لغات برمجة أخرى؟
لا ، تم تصميم Aspose.Words for .NET خصيصًا لتطبيقات .NET. يعمل مع لغات البرمجة مثل C # و VB.NET.

#### س 4. هل هناك أي متطلبات أخرى لاستخدام Aspose.Words مع .NET؟
بالإضافة إلى تثبيت مكتبة Aspose.Words for .NET ، يجب أن تكون لديك معرفة أساسية ببرمجة C # ومعالجة الكلمات باستخدام مستندات Word. الإلمام بـ .NET framework سيكون مفيدًا أيضًا.
