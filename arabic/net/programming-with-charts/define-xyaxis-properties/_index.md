---
title: حدد خصائص محور س ص في مخطط
linktitle: حدد خصائص محور س ص في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحديد خصائص المحور XY في مخطط باستخدام Aspose.Words for .NET. يتم عرض خيارات التخصيص للمحاور X و Y.
type: docs
weight: 10
url: /ar/net/programming-with-charts/define-xyaxis-properties/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعريف خصائص محوري X و Y في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات سلسلة وتخصيص خصائص المحور.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستند الناتج.

## الخطوة 2: أنشئ مستندًا جديدًا وأدخل مخططًا

 إنشاء ملف`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك ، أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder`. في هذا المثال ، سنقوم بإدراج مخطط مساحي.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف خمس نقاط بيانات مع التواريخ والقيم المقابلة.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## الخطوة 4: تخصيص خصائص المحور X و Y.

 لتخصيص خصائص المحورين X و Y ، قم بالوصول إلى`ChartAxis` الكائنات المرتبطة بالرسم البياني.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 قم بتعديل خصائص ملف`xAxis` و`yAxis`كائنات لتعيين الخيارات المرغوبة للمحاور X و Y. في هذا المثال ، سنوضح بعض الخصائص الشائعة التي يمكن تخصيصها.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

هذا يكمل تنفيذ تعريف خصائص المحور XY في مخطط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Define XYAxis Properties باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// إدراج الرسم البياني
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// قم بتغيير المحور X ليكون فئة بدلاً من التاريخ ، لذلك سيتم وضع جميع النقاط بفاصل زمني متساوي على المحور X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // تقاس بوحدات عرض المحور ص (مئات).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تحديد خصائص محوري X و Y في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص خصائص المحور لتلبية متطلباتك المحددة. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات شاملة لمعالجة الكلمات مع مخططات في مستندات Word ، مما يسمح لك بمعالجة الجوانب المختلفة للمخطط ، بما في ذلك المحاور.

 من خلال الوصول إلى`ChartAxis` الكائنات المرتبطة بالمخطط ، يمكنك تعديل الخصائص مثل نوع الفئة وتقاطعات المحاور وعلامات التجزئة ومواضع التسمية والقياس والمزيد. تتيح لك هذه المرونة تخصيص مظهر وسلوك محاور المخطط لتقديم بياناتك بشكل فعال.

باستخدام Aspose.Words for .NET ، يمكنك دمج إمكانيات إنشاء المخططات والتخصيص بسلاسة في تطبيقات .NET وأتمتة إنشاء مستندات ذات مظهر احترافي مع تصورات غنية.

### أسئلة وأجوبة

#### س 1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء مستندات Word ومعالجتها وحفظها برمجيًا في تطبيقات .NET. يوفر مجموعة كبيرة من الميزات لمعالجة الكلمات مع عناصر المستند ، بما في ذلك المخططات.

#### س 2. كيف يمكنني تثبيت Aspose.Words for .NET؟
يمكنك تثبيت Aspose.Words for .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س 3. هل يمكنني تخصيص جوانب أخرى من المخطط باستخدام Aspose.Words for .NET؟
نعم ، يوفر Aspose.Words for .NET إمكانيات واسعة لتخصيص الجوانب المختلفة للمخطط. بالإضافة إلى تحديد خصائص المحور ، يمكنك تعديل نوع المخطط وسلسلة البيانات ووسيلة الإيضاح والعنوان ومنطقة الرسم وتسميات البيانات والعديد من العناصر الأخرى في المخطط. توفر واجهة برمجة التطبيقات تحكمًا دقيقًا في مظهر الرسم البياني وسلوكه.

#### س 4. هل يمكنني إنشاء أنواع مختلفة من المخططات باستخدام Aspose.Words for .NET؟
نعم ، يدعم Aspose.Words for .NET مجموعة كبيرة من أنواع المخططات ، بما في ذلك المنطقة والشريط والخط والفطيرة والمبعثر والمزيد. يمكنك استخدام ال`ChartType` التعداد لتحديد نوع المخطط المطلوب عند إدراج شكل مخطط في مستند Word.

#### س 5. هل يمكنني حفظ الرسم البياني بتنسيقات مختلفة؟
 نعم ، يتيح لك Aspose.Words for .NET حفظ المستند الذي يحتوي على الرسم البياني بتنسيقات مختلفة ، مثل DOCX و PDF و HTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند.

#### س 6. هل يمكنني تطبيق هذه الأساليب على مخططات متعددة في مستند؟
 نعم ، يمكنك تطبيق هذه الأساليب على مخططات متعددة في مستند عن طريق تكرار الخطوات اللازمة لكل مخطط. يمكنك إنشاء ملفات`Chart` و`ChartAxis` كائنات لكل مخطط وتخصيص خصائصها وفقًا لذلك. يوفر Aspose.Words for .NET دعمًا كاملاً لمعالجة الكلمات مع مخططات متعددة في مستند واحد.