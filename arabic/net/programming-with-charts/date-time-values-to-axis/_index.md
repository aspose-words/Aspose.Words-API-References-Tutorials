---
title: أضف قيم التاريخ والوقت إلى محور المخطط
linktitle: أضف قيم التاريخ والوقت إلى محور المخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إضافة قيم التاريخ والوقت إلى محور الرسم البياني باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/date-time-values-to-axis/
---

يشرح هذا البرنامج التعليمي كيفية إضافة قيم التاريخ والوقت إلى محور الرسم البياني باستخدام Aspose.Words for .NET.

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

## الخطوة 3: إدراج وتكوين شكل مخطط
 قم بإدراج شكل مخطط في المستند باستخدام امتداد`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع الرسم البياني والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## الخطوة 4: أضف البيانات إلى الرسم البياني
أضف البيانات إلى سلسلة المخطط ، بما في ذلك قيم التاريخ والوقت.

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
قم بتكوين المحور X للمخطط لعرض قيم التاريخ والوقت.

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
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### مثال على شفرة المصدر لـ Date Time Values To Axis باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
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
	// اضبط الوحدات الرئيسية على أسبوع والوحدات الثانوية ليوم واحد.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

ينشئ رمز المثال هذا مستند Word جديدًا ، ويدرج مخططًا عموديًا بقيم وقت التاريخ على المحور X ، ويحفظ المستند في الدليل المحدد.

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية إضافة قيم وقت التاريخ إلى محور الرسم البياني باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إنشاء مخطط وإضافة قيم وقت التاريخ إلى السلسلة وتكوين المحور لعرض قيم وقت التاريخ بدقة. يوفر Aspose.Words for .NET مجموعة قوية من الميزات لمعالجة الكلمات مع مخططات في مستندات Word ، مما يسمح لك بتمثيل وتصور البيانات بقيم التاريخ والوقت بشكل فعال.

### أسئلة وأجوبة

#### س 1. هل يمكنني إضافة قيم التاريخ والوقت إلى محور الرسم البياني باستخدام Aspose.Words for .NET؟
نعم ، باستخدام Aspose.Words for .NET ، يمكنك إضافة قيم وقت التاريخ وعرضها على محور الرسم البياني في مستند Word. يوفر Aspose.Words واجهات برمجة تطبيقات ووظائف للعمل مع أنواع المخططات المختلفة وتخصيص مظهرها ، بما في ذلك معالجة قيم وقت التاريخ على المحور.

#### س 2. كيف أقوم بإضافة قيم التاريخ والوقت إلى سلسلة الرسم البياني؟
 لإضافة قيم التاريخ والوقت إلى سلسلة المخطط ، يمكنك استخدام`Add`طريقة سلسلة الرسم البياني. قم بتوفير مصفوفة من قيم وقت التاريخ كبيانات الفئة (المحور السيني) ، جنبًا إلى جنب مع قيم السلاسل المقابلة. يتيح لك ذلك رسم نقاط البيانات بقيم وقت التاريخ على الرسم البياني.

#### س 3. كيف يمكنني تكوين المحور لعرض قيم التاريخ والوقت؟
 يمكنك تكوين محور المخطط لعرض قيم وقت التاريخ من خلال تعيين الخصائص المناسبة. على سبيل المثال ، يمكنك تحديد الحد الأدنى والحد الأقصى لقيم المحور باستخدام`Scaling.Minimum` و`Scaling.Maximum` الخصائص ، على التوالي. بالإضافة إلى ذلك ، يمكنك تعيين الوحدات الرئيسية والثانوية لتعريف الفاصل الزمني وعلامات التجزئة للمحور.
