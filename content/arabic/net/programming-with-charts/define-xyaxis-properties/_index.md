---
title: تحديد خصائص المحور XY في الرسم البياني
linktitle: تحديد خصائص المحور XY في الرسم البياني
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد خصائص المحور XY في المخطط باستخدام Aspose.Words لـ .NET. يتم عرض خيارات التخصيص للمحورين X وY.
type: docs
weight: 10
url: /ar/net/programming-with-charts/define-xyaxis-properties/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words لـ .NET لتحديد خصائص المحورين X وY في المخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص خصائص المحور.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستند الإخراج.

## الخطوة 2: إنشاء مستند جديد وإدراج مخطط

 إنشاء جديد`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك، قم بإدراج مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder`. في هذا المثال، سنقوم بإدراج مخطط مساحي.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: إضافة بيانات السلسلة إلى المخطط

أضف بيانات السلسلة إلى المخطط. في هذا المثال، سنضيف خمس نقاط بيانات بالتواريخ والقيم المقابلة.

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

## الخطوة 4: تخصيص خصائص المحورين X وY

 لتخصيص خصائص المحورين X وY، قم بالوصول إلى`ChartAxis` الكائنات المرتبطة بالمخطط.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 تعديل خصائص`xAxis` و`yAxis`الكائنات لتعيين الخيارات المطلوبة للمحورين X وY. في هذا المثال، سنوضح بعض الخصائص الشائعة التي يمكن تخصيصها.

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

 وأخيرًا، احفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

يكمل هذا تنفيذ تحديد خصائص المحور XY في المخطط باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لتحديد خصائص XYAxis باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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
	// قم بتغيير المحور X ليكون فئة بدلاً من التاريخ، بحيث يتم وضع جميع النقاط بفواصل متساوية على المحور X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //تقاس بوحدات العرض للمحور Y (المئات).
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

في هذا البرنامج التعليمي، تعلمت كيفية تحديد خصائص المحورين X وY في المخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة، يمكنك إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص خصائص المحور لتلبية متطلباتك المحددة. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات شاملة لمعالجة الكلمات باستخدام المخططات في مستندات Word، مما يسمح لك بمعالجة الجوانب المختلفة للمخطط، بما في ذلك المحاور.

من خلال الوصول إلى`ChartAxis` الكائنات المرتبطة بالمخطط، يمكنك تعديل خصائص مثل نوع الفئة، وتقاطعات المحاور، وعلامات التجزئة، ومواضع التسمية، والقياس، والمزيد. تمكنك هذه المرونة من تخصيص مظهر وسلوك محاور المخطط لتقديم بياناتك بشكل فعال.

باستخدام Aspose.Words for .NET، يمكنك دمج إمكانيات إنشاء المخططات والتخصيص بسلاسة في تطبيقات .NET الخاصة بك وأتمتة إنشاء مستندات ذات مظهر احترافي مع تصورات غنية.

### الأسئلة الشائعة

#### س1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء مستندات Word ومعالجتها وحفظها برمجيًا في تطبيقات .NET. فهو يوفر نطاقًا واسعًا من الميزات لمعالجة الكلمات باستخدام عناصر المستند، بما في ذلك المخططات.

#### س2. كيف يمكنني تثبيت Aspose.Words لـ .NET؟
يمكنك تثبيت Aspose.Words لـ .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س3. هل يمكنني تخصيص جوانب أخرى من المخطط باستخدام Aspose.Words لـ .NET؟
نعم، يوفر Aspose.Words for .NET إمكانات واسعة النطاق لتخصيص الجوانب المختلفة للمخطط. بالإضافة إلى تحديد خصائص المحور، يمكنك تعديل نوع المخطط وسلسلة البيانات ووسيلة الإيضاح والعنوان ومنطقة الرسم وتسميات البيانات والعديد من العناصر الأخرى للمخطط. توفر واجهة برمجة التطبيقات (API) تحكمًا دقيقًا في مظهر المخطط وسلوكه.

#### س 4. هل يمكنني إنشاء أنواع مختلفة من المخططات باستخدام Aspose.Words لـ .NET؟
 نعم، يدعم Aspose.Words for .NET نطاقًا واسعًا من أنواع المخططات، بما في ذلك المنطقة والشريط والخط والدائري والمبعثر والمزيد. يمكنك استخدام ال`ChartType` التعداد لتحديد نوع المخطط المطلوب عند إدراج شكل مخطط في مستند Word.

#### س5. هل يمكنني حفظ المخطط بتنسيقات مختلفة؟
نعم، يسمح لك Aspose.Words for .NET بحفظ المستند الذي يحتوي على المخطط بتنسيقات مختلفة، مثل DOCX وPDF وHTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام`Save` طريقة`Document` كائن لحفظ المستند.

#### س6. هل يمكنني تطبيق هذه التقنيات على مخططات متعددة في مستند؟
 نعم، يمكنك تطبيق هذه التقنيات على مخططات متعددة في المستند عن طريق تكرار الخطوات اللازمة لكل مخطط. يمكنك إنشاء منفصلة`Chart` و`ChartAxis` كائنات لكل مخطط وتخصيص خصائصها وفقًا لذلك. يوفر Aspose.Words for .NET الدعم الكامل لمعالجة الكلمات باستخدام مخططات متعددة في مستند واحد.