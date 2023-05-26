---
title: سلسلة مخطط واحد
linktitle: سلسلة مخطط واحد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تخصيص سلسلة مخططات مفردة في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/single-chart-series/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتخصيص سلسلة مخططات مفردة في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط والوصول إلى سلسلة معينة وتعديل خصائصها.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
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
	// المسار إلى دليل المستند الخاص بك
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