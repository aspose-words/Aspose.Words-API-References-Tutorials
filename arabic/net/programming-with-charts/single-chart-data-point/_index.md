---
title: تخصيص نقطة بيانات مخطط واحد في مخطط
linktitle: تخصيص نقطة بيانات مخطط واحد في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/single-chart-data-point/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتخصيص نقطة بيانات واحدة في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط والوصول إلى نقاط بيانات محددة وتعديل خصائصها.

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

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط خطي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: الوصول إلى نقاط البيانات وتخصيصها

 لتعديل نقاط البيانات الفردية ، تحتاج إلى الوصول إلى ملف`ChartDataPointCollection` من السلسلة وحدد نقطة البيانات المطلوبة باستخدام الفهرس.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

هذا يكمل تنفيذ تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لنقطة بيانات الرسم البياني الفردي باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد ، وإدراج مخطط خطي ، والوصول إلى نقاط بيانات محددة ضمن سلسلة المخطط ، وتعديل خصائصها لتحقيق التخصيص المطلوب.

يوفر Aspose.Words for .NET ميزات قوية لمعالجة المخططات في مستندات Word. من خلال الوصول إلى نقاط البيانات الفردية ضمن سلسلة مخطط ، يمكنك تطبيق تعديلات معينة لتخصيص مظهرها وسلوكها. يسمح لك هذا بتمييز نقاط بيانات محددة وتغيير رموز العلامات وضبط أحجام العلامات والمزيد لتحسين التمثيل المرئي للمخطط.

يمنحك تخصيص نقاط البيانات الفردية المرونة للتأكيد على البيانات المهمة أو إبراز اتجاهات معينة في المخطط الخاص بك. باستخدام Aspose.Words for .NET ، يمكنك الوصول بسهولة إلى نقاط البيانات وتعديلها في أنواع مخططات مختلفة ، مما يتيح لك إنشاء مخططات جذابة بصريًا وغنية بالمعلومات في مستندات Word الخاصة بك.

### أسئلة وأجوبة

#### س 1. هل يمكنني تخصيص نقاط بيانات متعددة في مخطط؟
 نعم ، يمكنك تخصيص نقاط بيانات متعددة في مخطط باستخدام Aspose.Words for .NET. من خلال الوصول إلى`ChartDataPointCollection`من سلسلة ، يمكنك تحديد نقاط بيانات متعددة وتعديلها بناءً على فهارسها. استخدم حلقة أو تخصيصات فردية لتعديل الخصائص المرغوبة لكل نقطة بيانات. بهذه الطريقة ، يمكنك تطبيق تخصيصات مختلفة على نقاط بيانات متعددة داخل نفس المخطط.

#### س 2. كيف يمكنني تغيير رمز العلامة لنقطة بيانات؟
 لتغيير رمز العلامة لنقطة بيانات في مخطط باستخدام Aspose.Words for .NET ، تحتاج إلى الوصول إلى ملف`Marker` ممتلكات`ChartDataPoint` كائن وتعيين`Symbol` إلى رمز العلامة المطلوب. تمثل رموز العلامة الشكل أو الرمز المستخدم لتمثيل كل نقطة بيانات على الرسم البياني. يمكنك الاختيار من بين مجموعة متنوعة من رموز العلامات المضمنة مثل الدائرة والمربع والماس والمثلث والنجمة والمزيد.

#### س 3. هل يمكنني ضبط حجم علامة نقطة البيانات؟
 نعم ، يمكنك ضبط حجم علامة نقطة البيانات في مخطط باستخدام Aspose.Words for .NET. الوصول إلى`Marker` ممتلكات`ChartDataPoint` كائن وتعيين`Size`الخاصية لحجم العلامة المطلوب. عادةً ما يتم تحديد حجم العلامة بالنقاط ، حيث تمثل القيمة الأكبر حجمًا أكبر للعلامة. يتيح لك ضبط حجم العلامة التأكيد على نقاط بيانات محددة أو التمييز بينها بناءً على أهميتها.

#### س 4. ما الخصائص الأخرى التي يمكنني تعديلها لنقطة بيانات؟
يوفر Aspose.Words for .NET مجموعة من الخصائص التي يمكنك تعديلها لنقطة بيانات في مخطط. تتضمن بعض الخصائص المعدلة بشكل شائع رمز العلامة ، وحجم العلامة ، ولون العلامة ، ورؤية تسمية البيانات ، والانفجار ، والعكس إذا كان سالبًا ، والمزيد. تتيح لك هذه الخصائص تخصيص المظهر والسلوك والتفاعل لنقاط البيانات الفردية ، مما يتيح لك إنشاء مخططات مصممة وفقًا لمتطلباتك المحددة.

#### س 5. هل يمكنني تخصيص نقاط البيانات في أنواع المخططات الأخرى؟
نعم ، يمكنك تخصيص نقاط البيانات في أنواع مخططات مختلفة باستخدام Aspose.Words for .NET. بينما يوضح هذا البرنامج التعليمي تخصيص نقاط البيانات في مخطط خطي ، يمكنك تطبيق تقنيات مماثلة على أنواع المخططات الأخرى مثل المخططات العمودية والمخططات الشريطية والمخططات الدائرية والمزيد. تتضمن العملية الوصول إلى السلاسل ونقاط البيانات داخل المخطط وتعديل خصائصها وفقًا لذلك.