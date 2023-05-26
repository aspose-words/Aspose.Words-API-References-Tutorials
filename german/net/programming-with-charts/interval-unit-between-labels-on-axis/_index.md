---
title: وحدة الفاصل الزمني بين التسميات على المحور
linktitle: وحدة الفاصل الزمني بين التسميات على المحور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين وحدة الفاصل الزمني بين التسميات على محور الرسم البياني باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين وحدة الفاصل بين التسميات على محور الرسم البياني. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات سلسلة وتخصيص تسميات المحور.

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

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط عمودي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف خمسة عناصر بقيمها المقابلة.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## الخطوة 4: تخصيص تسميات المحور

 لتعيين وحدة الفاصل الزمني بين التسميات على المحور X ، قم بالوصول إلى ملف`AxisX` خاصية الرسم البياني وتعيين`TickLabelSpacing` إلى القيمة المطلوبة. في هذا المثال ، قمنا بتعيين التباعد على 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

هذا يكمل تنفيذ إعداد وحدة الفاصل الزمني بين الملصقات على المحور باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لوحدة الفاصل الزمني بين الملصقات على المحور باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```