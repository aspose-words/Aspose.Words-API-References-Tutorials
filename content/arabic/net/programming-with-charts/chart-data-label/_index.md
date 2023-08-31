---
title: تخصيص تسمية بيانات المخطط
linktitle: تخصيص تسمية بيانات المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET لتوفير معلومات إضافية حول نقاط البيانات.
type: docs
weight: 10
url: /ar/net/programming-with-charts/chart-data-label/
---

يشرح هذا البرنامج التعليمي كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET. توفر تسميات البيانات معلومات إضافية حول نقاط البيانات في المخطط.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وDocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج مخطط وتكوينه
 قم بإدراج مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع المخطط والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: تخصيص تسميات البيانات
يمكنك الوصول إلى مجموعة تسميات البيانات الخاصة بسلسلة المخططات وتعديل الخصائص المتنوعة لتخصيص مظهر تسميات البيانات.

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
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### مثال على التعليمات البرمجية المصدر لتسمية بيانات المخطط باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// بشكل افتراضي، عند إضافة تسميات البيانات إلى نقاط البيانات في مخطط دائري، يتم عرض الخطوط السابقة لتسميات البيانات التي
	// يتم وضعه بعيدًا عن نهاية نقاط البيانات. تنشئ الخطوط الرئيسية اتصالاً مرئيًا بين تسمية البيانات وبياناتها
	// نقطة البيانات المقابلة
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
في هذا البرنامج التعليمي، تعلمت كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة، يمكنك إدراج مخطط والوصول إلى مجموعة تسميات البيانات وتعديل الخصائص لتخصيص مظهر تسميات البيانات. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام مستندات ومخططات Word، مما يتيح لك إنشاء مخططات جذابة وغنية بالمعلومات مع تسميات بيانات مخصصة.

### الأسئلة الشائعة

#### س1. ما هي تسميات البيانات في المخطط؟
توفر تسميات البيانات في المخطط معلومات إضافية حول نقاط البيانات الممثلة في المخطط. يمكنهم عرض القيم أو الفئات أو أسماء السلاسل أو النسب المئوية أو التفاصيل الأخرى ذات الصلة اعتمادًا على نوع المخطط والتكوين.

#### س2. هل يمكنني تخصيص مظهر تسميات البيانات؟
نعم، يمكنك تخصيص مظهر تسميات البيانات في المخطط. يوفر Aspose.Words for .NET خيارات لتعديل الخصائص المتنوعة لتسميات البيانات، مثل إظهار مفاتيح وسيلة الإيضاح والسطور السابقة وأسماء الفئات وأسماء السلاسل والقيم والمزيد. يمكنك أيضًا تعيين الفواصل وتنسيق التسميات لتلبية متطلباتك المحددة.

#### س3. هل يمكنني إضافة تسميات البيانات إلى أي نوع مخطط؟
نعم، يمكنك إضافة تسميات البيانات إلى أنواع مختلفة من المخططات، بما في ذلك المخططات الشريطية والمخططات الدائرية والمخططات الخطية والمزيد. قد تختلف عملية إضافة تسميات البيانات وتخصيصها قليلاً حسب نوع المخطط والمكتبة أو الأداة التي تستخدمها.
