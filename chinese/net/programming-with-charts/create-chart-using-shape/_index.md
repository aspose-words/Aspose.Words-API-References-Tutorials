---
title: إنشاء مخطط باستخدام الشكل
linktitle: إنشاء مخطط باستخدام الشكل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء مخطط وتخصيصه باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-charts/create-chart-using-shape/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: إدراج وتكوين شكل مخطط
 قم بإدراج شكل مخطط في المستند باستخدام امتداد`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع الرسم البياني والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: تخصيص الرسم البياني
قم بتخصيص المخطط عن طريق تعديل الخصائص المختلفة مثل عنوان المخطط ووسيلة الإيضاح.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save`طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### مثال على التعليمات البرمجية المصدر لإنشاء مخطط باستخدام الشكل باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// يرجى ملاحظة أنه إذا تم تحديد قيمة خالية أو فارغة كنص عنوان ، فسيتم عرض العنوان الذي تم إنشاؤه تلقائيًا.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

هذا كل شيء! لقد نجحت في إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.