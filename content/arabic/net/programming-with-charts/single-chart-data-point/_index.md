---
title: تخصيص نقطة بيانات مخطط واحد في المخطط
linktitle: تخصيص نقطة بيانات مخطط واحد في المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/single-chart-data-point/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتخصيص نقطة بيانات واحدة في المخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط والوصول إلى نقاط بيانات محددة وتعديل خصائصها.

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

 بعد ذلك، استخدم`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط خطي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: الوصول إلى نقاط البيانات وتخصيصها

 لتعديل نقاط البيانات الفردية، تحتاج إلى الوصول إلى`ChartDataPointCollection` من السلسلة وحدد نقطة البيانات المطلوبة باستخدام الفهرس.

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

 وأخيرًا، احفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

يكمل هذا تنفيذ تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لنقطة بيانات المخطط الفردي باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، تعلمت كيفية تخصيص نقطة بيانات واحدة في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك إنشاء مستند جديد وإدراج مخطط خطي والوصول إلى نقاط بيانات محددة ضمن سلسلة المخططات وتعديل خصائصها لتحقيق التخصيص المطلوب.

يوفر Aspose.Words for .NET ميزات قوية لمعالجة المخططات في مستندات Word. من خلال الوصول إلى نقاط البيانات الفردية ضمن سلسلة المخططات، يمكنك تطبيق تعديلات محددة لتخصيص مظهرها وسلوكها. يتيح لك ذلك تمييز نقاط بيانات محددة وتغيير رموز العلامات وضبط أحجام العلامات والمزيد لتحسين التمثيل المرئي للمخطط الخاص بك.

يمنحك تخصيص نقاط البيانات الفردية المرونة اللازمة للتأكيد على البيانات المهمة أو إبراز اتجاهات معينة في المخطط الخاص بك. باستخدام Aspose.Words for .NET، يمكنك بسهولة الوصول إلى نقاط البيانات وتعديلها في أنواع مختلفة من المخططات، مما يتيح لك إنشاء مخططات جذابة وغنية بالمعلومات في مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س1. هل يمكنني تخصيص نقاط بيانات متعددة في مخطط؟
 نعم، يمكنك تخصيص نقاط بيانات متعددة في مخطط باستخدام Aspose.Words for .NET. من خلال الوصول إلى`ChartDataPointCollection`من سلسلة، يمكنك تحديد وتعديل نقاط بيانات متعددة بناءً على مؤشراتها. استخدم حلقة أو مهام فردية لتعديل الخصائص المطلوبة لكل نقطة بيانات. بهذه الطريقة، يمكنك تطبيق تخصيصات مختلفة على نقاط بيانات متعددة داخل نفس المخطط.

#### س2. كيف يمكنني تغيير رمز العلامة لنقطة البيانات؟
 لتغيير رمز العلامة لنقطة بيانات في مخطط باستخدام Aspose.Words for .NET، تحتاج إلى الوصول إلى`Marker` ملكية`ChartDataPoint` الكائن وتعيين`Symbol` الخاصية إلى رمز العلامة المطلوب. تمثل رموز العلامة الشكل أو الرمز المستخدم لتمثيل كل نقطة بيانات على المخطط. يمكنك الاختيار من بين مجموعة متنوعة من رموز التحديد المضمنة مثل الدائرة والمربع والمعين والمثلث والنجمة والمزيد.

#### س3. هل يمكنني ضبط حجم علامة نقطة البيانات؟
 نعم، يمكنك ضبط حجم علامة نقطة البيانات في المخطط باستخدام Aspose.Words for .NET. الوصول إلى`Marker` ملكية`ChartDataPoint` الكائن وتعيين`Size`الخاصية إلى حجم العلامة المطلوبة. يتم تحديد حجم العلامة عادةً بالنقاط، حيث تمثل القيمة الأكبر حجمًا أكبر للعلامة. يتيح لك ضبط حجم العلامة التركيز على نقاط بيانات محددة أو التمييز بينها بناءً على أهميتها.

#### س 4. ما هي الخصائص الأخرى التي يمكنني تعديلها لنقطة البيانات؟
يوفر Aspose.Words for .NET نطاقًا من الخصائص التي يمكنك تعديلها لنقطة بيانات في المخطط. تتضمن بعض الخصائص المعدلة بشكل شائع رمز العلامة، وحجم العلامة، ولون العلامة، ورؤية تسمية البيانات، والانفجار، والعكس إذا كانت سلبية، والمزيد. تسمح لك هذه الخصائص بتخصيص مظهر نقاط البيانات الفردية وسلوكها وتفاعلها، مما يتيح لك إنشاء مخططات مخصصة وفقًا لمتطلباتك المحددة.

#### س5. هل يمكنني تخصيص نقاط البيانات في أنواع المخططات الأخرى؟
نعم، يمكنك تخصيص نقاط البيانات في أنواع مختلفة من المخططات باستخدام Aspose.Words for .NET. بينما يوضح هذا البرنامج التعليمي تخصيص نقاط البيانات في المخطط الخطي، يمكنك تطبيق تقنيات مشابهة على أنواع المخططات الأخرى مثل المخططات العمودية، والمخططات الشريطية، والمخططات الدائرية، والمزيد. تتضمن العملية الوصول إلى السلاسل ونقاط البيانات الموجودة داخل المخطط وتعديل خصائصها وفقًا لذلك.