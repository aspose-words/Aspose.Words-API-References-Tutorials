---
title: تخصيص تسمية بيانات المخطط
linktitle: تخصيص تسمية بيانات المخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET لتوفير معلومات إضافية حول نقاط البيانات.
type: docs
weight: 10
url: /ar/net/programming-with-charts/chart-data-label/
---

يشرح هذا البرنامج التعليمي كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET. توفر تسميات البيانات معلومات إضافية حول نقاط البيانات في مخطط.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج وتكوين مخطط
 أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع الرسم البياني والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: تخصيص تسميات البيانات
قم بالوصول إلى مجموعة تسميات البيانات لسلسلة المخطط وتعديل الخصائص المختلفة لتخصيص مظهر تسميات البيانات.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### مثال على شفرة المصدر لتسمية بيانات المخطط باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// بشكل افتراضي ، عند إضافة تسميات البيانات إلى نقاط البيانات في مخطط دائري ، يتم عرض الخطوط السابقة لتسميات البيانات
	// تم وضعه بعيدًا عن نهاية نقاط البيانات. تنشئ خطوط القائد اتصالاً مرئيًا بين تسمية البيانات و
	// نقطة البيانات المقابلة.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

هذا كل شيء! لقد نجحت في إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET.

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إدراج مخطط والوصول إلى مجموعة تسميات البيانات وتعديل الخصائص لتخصيص مظهر تسميات البيانات. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام مستندات ومخططات Word ، مما يتيح لك إنشاء مخططات جذابة بصريًا وغنية بالمعلومات مع تسميات بيانات مخصصة.

### أسئلة وأجوبة

#### س 1. ما هي تسميات البيانات في الرسم البياني؟
توفر تسميات البيانات في مخطط معلومات إضافية حول نقاط البيانات الممثلة في المخطط. يمكنهم عرض القيم أو الفئات أو أسماء السلاسل أو النسب المئوية أو تفاصيل أخرى ذات صلة بناءً على نوع المخطط والتكوين.

#### س 2. هل يمكنني تخصيص مظهر تسميات البيانات؟
نعم ، يمكنك تخصيص مظهر تسميات البيانات في مخطط. يوفر Aspose.Words for .NET خيارات لتعديل الخصائص المختلفة لتسميات البيانات ، مثل إظهار مفاتيح وسيلة الإيضاح وخطوط القائد وأسماء الفئات وأسماء السلاسل والقيم والمزيد. يمكنك أيضًا تعيين الفواصل وتنسيق الملصقات لتلبية متطلباتك المحددة.

#### س 3. هل يمكنني إضافة تسميات البيانات إلى أي نوع من المخططات؟
نعم ، يمكنك إضافة تسميات البيانات إلى أنواع مختلفة من المخططات ، بما في ذلك المخططات الشريطية والمخططات الدائرية والمخططات الخطية والمزيد. قد تختلف عملية إضافة تسميات البيانات وتخصيصها قليلاً حسب نوع المخطط والمكتبة أو الأداة التي تستخدمها.
