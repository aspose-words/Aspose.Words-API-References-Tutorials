---
title: إضافة قيم التاريخ والوقت إلى محور المخطط
linktitle: إضافة قيم التاريخ والوقت إلى محور المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/date-time-values-to-axis/
---

يشرح هذا البرنامج التعليمي كيفية إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words for .NET.

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

## الخطوة 3: إدراج شكل مخطط وتكوينه
 قم بإدراج شكل مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع المخطط والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## الخطوة 4: إضافة البيانات إلى المخطط
إضافة بيانات إلى سلسلة المخطط، بما في ذلك قيم التاريخ والوقت.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## الخطوة 5: تكوين المحور
قم بتكوين المحور السيني للمخطط لعرض قيم التاريخ والوقت.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### مثال على التعليمات البرمجية المصدر لقيم التاريخ والوقت إلى المحور باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// قم بتعيين الوحدات الرئيسية على أسبوع والوحدات الثانوية على يوم واحد.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

يقوم نموذج التعليمات البرمجية هذا بإنشاء مستند Word جديد، وإدراج مخطط عمودي بقيم التاريخ والوقت على المحور السيني، وحفظ المستند في الدليل المحدد.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة، يمكنك إنشاء مخطط وإضافة قيم التاريخ والوقت إلى السلسلة وتكوين المحور لعرض قيم التاريخ والوقت بدقة. يوفر Aspose.Words for .NET مجموعة قوية من الميزات لمعالجة الكلمات باستخدام المخططات في مستندات Word، مما يسمح لك بتمثيل البيانات وتصورها باستخدام قيم التاريخ والوقت بشكل فعال.

### الأسئلة الشائعة

#### س1. هل يمكنني إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words لـ .NET؟
نعم، باستخدام Aspose.Words for .NET، يمكنك إضافة قيم التاريخ والوقت وعرضها على محور المخطط في مستند Word. يوفر Aspose.Words واجهات برمجة التطبيقات والوظائف للعمل مع أنواع المخططات المختلفة وتخصيص مظهرها، بما في ذلك التعامل مع قيم التاريخ والوقت على المحور.

#### س2. كيف أقوم بإضافة قيم التاريخ والوقت إلى سلسلة المخططات؟
 لإضافة قيم التاريخ والوقت إلى سلسلة المخططات، يمكنك استخدام`Add`طريقة سلسلة الرسم البياني. قم بتوفير مصفوفة من قيم التاريخ والوقت كبيانات الفئة (المحور السيني)، بالإضافة إلى قيم السلسلة المقابلة. يتيح لك ذلك رسم نقاط البيانات بقيم التاريخ والوقت على المخطط.

#### س3. كيف يمكنني تكوين المحور لعرض قيم التاريخ والوقت؟
 يمكنك تكوين محور المخطط لعرض قيم التاريخ والوقت عن طريق تعيين الخصائص المناسبة. على سبيل المثال، يمكنك تحديد الحد الأدنى والحد الأقصى لقيم المحور باستخدام`Scaling.Minimum` و`Scaling.Maximum` الخصائص، على التوالي. بالإضافة إلى ذلك، يمكنك تعيين الوحدات الرئيسية والثانوية لتحديد الفاصل الزمني وعلامات التجزئة للمحور.
