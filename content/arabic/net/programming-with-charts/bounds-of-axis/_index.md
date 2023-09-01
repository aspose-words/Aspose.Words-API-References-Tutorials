---
title: حدود المحور في الرسم البياني
linktitle: حدود المحور في الرسم البياني
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين حدود المحور في المخطط باستخدام Aspose.Words لـ .NET للتحكم في نطاق القيم المعروضة على المحور.
type: docs
weight: 10
url: /ar/net/programming-with-charts/bounds-of-axis/
---

يشرح هذا البرنامج التعليمي كيفية تعيين حدود المحور في المخطط باستخدام Aspose.Words لـ .NET. من خلال إدراج مخطط وإضافة بيانات متسلسلة وتكوين مقياس المحور، يمكنك تحديد الحد الأدنى والحد الأقصى لقيم المحور.

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

## الخطوة 3: إدراج مخطط وتكوينه
 قم بإدراج مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع المخطط والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: إضافة بيانات السلسلة
امسح أي سلسلة موجودة في المخطط وأضف بيانات سلسلة جديدة. في هذا المثال، نضيف سلسلة بالتسميات "العنصر 1" إلى "العنصر 5" والقيم المقابلة.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## الخطوة 5: تعيين حدود المحور
 قم بتكوين تحجيم المحور Y عن طريق تعيين الحد الأدنى والحد الأقصى للقيم باستخدام`Scaling.Minimum` و`Scaling.Maximum` خصائص المحور.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Bounds Of Axis باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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

هذا كل شيء! لقد نجحت في تعيين حدود المحور في المخطط باستخدام Aspose.Words لـ .NET.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية تعيين حدود المحور في المخطط باستخدام Aspose.Words for .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك إدراج مخطط وتكوينه وإضافة بيانات متسلسلة وتحديد الحد الأدنى والحد الأقصى للقيم لقياس المحور. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام مستندات Word، مما يسمح لك بإنشاء مخططات ديناميكية وجذابة بصريًا بسهولة.


### الأسئلة الشائعة

#### س1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة تتيح للمطورين العمل مع مستندات Word برمجيًا. فهو يوفر مجموعة واسعة من الميزات والوظائف لإنشاء مستندات Word ومعالجتها وحفظها.

#### س2. كيف يمكنني تثبيت Aspose.Words لـ .NET؟
لتثبيت Aspose.Words لـ .NET، يمكنك استخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س3. هل يمكنني استخدام Aspose.Words لـ .NET مع لغات البرمجة الأخرى؟
لا، Aspose.Words for .NET مصمم خصيصًا لتطبيقات .NET. يعمل مع لغات البرمجة مثل C# و VB.NET.

#### س 4. هل هناك أي متطلبات أساسية أخرى لاستخدام Aspose.Words لـ .NET؟
إلى جانب تثبيت مكتبة Aspose.Words for .NET، يجب أن تكون لديك معرفة أساسية ببرمجة C# ومعالجة الكلمات باستخدام مستندات Word. سيكون الإلمام بإطار عمل .NET مفيدًا أيضًا.
