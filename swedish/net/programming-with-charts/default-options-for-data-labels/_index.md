---
title: الخيارات الافتراضية لتسميات البيانات
linktitle: الخيارات الافتراضية لتسميات البيانات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/default-options-for-data-labels/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين الخيارات الافتراضية لتسميات البيانات في الرسم البياني. يوضح الكود المقدم كيفية إنشاء مخطط وإضافة سلسلة بيانات وتخصيص تسميات البيانات باستخدام Aspose.Words.

## الخطوة 1: قم بإعداد المشروع

قبل أن نبدأ ، تأكد من توفر المتطلبات التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستند الناتج.

## الخطوة 2: أنشئ مستندًا جديدًا وأدخل مخططًا

 أولاً ، لنقم بإنشاء ملف`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك ، نقوم بإدراج مخطط في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder`. في هذا المثال ، سنقوم بإدراج مخطط دائري.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف سلسلة البيانات إلى الرسم البياني

الآن ، دعنا نضيف سلسلة بيانات إلى المخطط. في هذا المثال ، سنضيف ثلاث فئات والقيم المقابلة لها.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## الخطوة 4: تخصيص تسميات البيانات

 لتخصيص تسميات البيانات في المخطط ، نحتاج إلى الوصول إلى ملف`ChartDataLabelCollection` الكائن المرتبط بالسلسلة.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 يمكننا بعد ذلك تعديل الخصائص المختلفة لملف`labels` لتعيين الخيارات المطلوبة لتسميات البيانات. في هذا المثال ، سنقوم بتمكين عرض النسبة المئوية والقيمة ، وتعطيل الخطوط البادئة ، وتعيين فاصل مخصص.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## الخطوة 5: احفظ المستند

 أخيرًا ، نحفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

هذا يكمل تنفيذ إعداد الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر للخيارات الافتراضية لعناوين البيانات باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```