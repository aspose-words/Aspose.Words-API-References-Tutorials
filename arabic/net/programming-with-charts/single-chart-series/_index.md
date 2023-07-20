---
title: تخصيص سلسلة مخطط واحد في مخطط
linktitle: تخصيص سلسلة مخطط واحد في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تخصيص سلسلة مخططات مفردة في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/single-chart-series/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتخصيص سلسلة مخططات مفردة في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط والوصول إلى سلسلة معينة وتعديل خصائصها.

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

## الخطوة 3: الوصول إلى سلسلة المخططات وتخصيصها

 لتعديل سلسلة مخططات مفردة ، تحتاج إلى الوصول إلى ملف`ChartSeries` كائنات الرسم البياني.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

هذا يكمل تنفيذ تخصيص سلسلة مخططات واحدة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لسلسلة مخطط واحد باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// يمكنك أيضًا تحديد ما إذا كان الخط الذي يربط النقاط على الرسم البياني سيتم تنعيمه باستخدام خطوط Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// يحدد ما إذا كان العنصر الأصلي سيعكس ألوانه افتراضيًا إذا كانت القيمة سالبة.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تخصيص سلسلة مخططات واحدة في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد ، وإدراج مخطط خطي ، والوصول إلى سلسلة مخططات محددة ، وتعديل خصائصها لتحقيق التخصيص المطلوب.

يوفر Aspose.Words for .NET ميزات قوية لمعالجة المخططات في مستندات Word. من خلال الوصول إلى سلسلة المخططات الفردية ، يمكنك تطبيق تعديلات محددة لتخصيص مظهرها وسلوكها. يتيح لك ذلك تغيير اسم السلسلة ، وتمكين تجانس خط المخطط ، وتخصيص علامات لنقاط البيانات ، وعكس الألوان للقيم السالبة ، والمزيد لتحسين التمثيل المرئي للمخطط.

يوفر لك تخصيص سلسلة مخططات مفردة المرونة لإبراز بيانات معينة أو التأكيد على اتجاهات معينة داخل المخطط الخاص بك. باستخدام Aspose.Words for .NET ، يمكنك الوصول بسهولة إلى خصائص سلسلة المخططات وتعديلها ، مما يتيح لك إنشاء مخططات جذابة ومفيدة بصريًا في مستندات Word الخاصة بك.

### أسئلة وأجوبة

#### س 1. هل يمكنني تخصيص سلاسل مخططات متعددة في مخطط؟
 نعم ، يمكنك تخصيص سلاسل مخططات متعددة في مخطط باستخدام Aspose.Words for .NET. من خلال الوصول إلى`ChartSeries`كائنات داخل المخطط ، يمكنك تحديد وتعديل سلاسل متعددة بناءً على فهارسها أو معايير محددة. استخدم حلقة أو تعيينات فردية لتعديل الخصائص المطلوبة لكل سلسلة مخطط. بهذه الطريقة ، يمكنك تطبيق تخصيصات مختلفة على سلاسل متعددة داخل نفس المخطط.

#### س 2. كيف يمكنني تغيير اسم سلسلة المخططات؟
 لتغيير اسم سلسلة المخططات في مخطط باستخدام Aspose.Words for .NET ، تحتاج إلى الوصول إلى ملف`Name` ممتلكات`ChartSeries` الكائن وتعيينه على الاسم المطلوب. يتم عرض اسم السلسلة عادةً في وسيلة إيضاح المخطط أو تسميات البيانات ، مما يوفر تسمية وصفية للسلسلة. من خلال تعديل اسم السلسلة ، يمكنك توفير أسماء ذات معنى تعكس البيانات التي تمثلها كل سلسلة.

#### س 3. ما هو تجانس سلسلة المخططات؟
تجانس سلسلة المخططات هو أسلوب تحسين مرئي يسمح لك بإنشاء خط سلس يربط بين النقاط على الرسم البياني. وهو يطبق خوارزمية تجانس ، مثل شرائح Catmull-Rom ، للاستيفاء بين نقاط البيانات وإنشاء منحنى ممتع بصريًا. لتمكين تجانس السلسلة في مخطط باستخدام Aspose.Words for .NET ، قم بالوصول إلى`Smooth` ممتلكات`ChartSeries` كائن وضبطه على`true`. يمكن أن يكون التجانس مفيدًا لعرض الاتجاهات أو الأنماط في البيانات ذات التقلبات غير المنتظمة.

#### س 4. كيف يمكنني تخصيص علامات لنقاط البيانات في سلسلة مخطط؟
 لتخصيص علامات لنقاط البيانات في سلسلة مخطط باستخدام Aspose.Words for .NET ، تحتاج إلى الوصول إلى`Marker` ممتلكات`ChartSeries` الكائن وتعديل خصائصه مثل`Symbol` و`Size`. العلامات هي مؤشرات مرئية توضع على الرسم البياني لتمثيل نقاط البيانات الفردية. يمكنك الاختيار من بين مجموعة متنوعة من رموز العلامات المضمنة وضبط حجمها لتمييز أو تمييز نقاط بيانات معينة داخل السلسلة.

#### س 5. هل يمكنني عكس الألوان للقيم السالبة في سلسلة المخططات؟
 نعم ، يمكنك عكس الألوان للقيم السالبة في سلسلة المخططات باستخدام Aspose.Words for .NET. عن طريق تحديد`InvertIfNegative` ممتلكات`ChartSeries` يعترض على`true`، سيتم عكس ألوان نقاط البيانات ذات القيم السالبة ، مما يجعلها مميزة بصريًا عن القيم الموجبة. يمكن أن تكون هذه الميزة مفيدة عند مقارنة القيم الإيجابية والسلبية في سلسلة مخططات ، مما يوفر تمايزًا واضحًا بين الاثنين.