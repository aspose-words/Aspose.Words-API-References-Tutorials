---
title: تنسيق الأرقام للمحور
linktitle: تنسيق الأرقام للمحور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين تنسيق الأرقام لمحور في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/number-format-for-axis/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين تنسيق الأرقام لمحور في الرسم البياني. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات سلسلة وتنسيق تسميات المحور.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## الخطوة 4: قم بتنسيق تسميات المحور

 لتعيين تنسيق الأرقام لتسميات المحور ص ، قم بالوصول إلى ملف`AxisY` خاصية الرسم البياني وتعيين`NumberFormat.FormatCode` إلى التنسيق المطلوب. في هذا المثال ، قمنا بتعيين التنسيق على "#، ## 0" لعرض الأرقام مع الآلاف من الفواصل.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

هذا يكمل تنفيذ إعداد تنسيق الأرقام للمحور باستخدام Aspose.Words for .NET.

### مثال على الكود المصدري لـ Number Format For Axis باستخدام Aspose.Words for .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```