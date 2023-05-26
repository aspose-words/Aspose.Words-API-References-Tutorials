---
title: تسمية بيانات المخطط
linktitle: تسمية بيانات المخطط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET لتوفير معلومات إضافية حول نقاط البيانات.
type: docs
weight: 10
url: /zh/net/programming-with-charts/chart-data-label/
---

يشرح هذا البرنامج التعليمي كيفية إضافة تسميات البيانات وتخصيصها في مخطط باستخدام Aspose.Words for .NET. توفر تسميات البيانات معلومات إضافية حول نقاط البيانات في مخطط.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

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
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//بشكل افتراضي ، عند إضافة تسميات البيانات إلى نقاط البيانات في مخطط دائري ، يتم عرض الخطوط السابقة لتسميات البيانات
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