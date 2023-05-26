---
title: تنسيق رقم تسمية البيانات
linktitle: تنسيق رقم تسمية البيانات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET. تخصيص تنسيقات الأرقام لتسميات البيانات بسهولة.
type: docs
weight: 10
url: /ru/net/programming-with-charts/format-number-of-data-label/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتنسيق عدد تسميات البيانات في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص تنسيق الأرقام لتسميات البيانات.

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

 بعد ذلك ، أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder`في هذا المثال ، سنقوم بإدراج مخطط خطي.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف ثلاث فئات والقيم المقابلة لها.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## الخطوة 4: تخصيص تنسيق الأرقام لتسميات البيانات

 لتنسيق عدد تسميات البيانات ، قم بالوصول إلى`DataLabels` المجموعة المرتبطة بالسلسلة.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

في هذا المثال ، قمنا بتعيين تنسيقات أرقام مختلفة لكل تسمية بيانات. تم تنسيق تسمية البيانات الأولى كعملة ، والثانية كتاريخ ، والثالثة كنسبة مئوية.

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

هذا يكمل تنفيذ تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لتنسيق رقم تسمية البيانات باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// حذف السلاسل التي تم إنشاؤها بشكل افتراضي.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// أو يمكنك تعيين كود التنسيق لربطه بخلية مصدر ،
	// في هذه الحالة ، سيتم إعادة تعيين NumberFormat إلى عام وسيتم توريثه من خلية مصدر.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```