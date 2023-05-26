---
title: إخفاء محور التخطيط
linktitle: إخفاء محور التخطيط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إخفاء محور الرسم البياني في مستند باستخدام Aspose.Words for .NET. إخفاء المحور لعرض مخطط أوضح وأكثر تركيزًا.
type: docs
weight: 10
url: /it/net/programming-with-charts/hide-chart-axis/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإخفاء محور المخطط في مستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات سلسلة وإخفاء محور المخطط.

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

 بعد ذلك ، أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder`. في هذا المثال ، سنقوم بإدراج مخطط عمودي.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف خمسة عناصر والقيم المقابلة لها.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## الخطوة 4: إخفاء محور المخطط

 لإخفاء محور المخطط ، قم بالوصول إلى ملف`AxisY` خاصية الرسم البياني وتعيين`Hidden` ملكية ل`true`.

```csharp
chart.AxisY.Hidden = true;
```

في هذا المثال ، نقوم بإخفاء المحور ص في الرسم البياني.

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

هذا يكمل تنفيذ إخفاء محور الرسم البياني باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإخفاء محور الرسم البياني باستخدام Aspose.Words for .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```