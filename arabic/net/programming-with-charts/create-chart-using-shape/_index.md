---
title: إنشاء وتخصيص الرسم البياني باستخدام الشكل
linktitle: إنشاء وتخصيص الرسم البياني باستخدام الشكل
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء مخطط وتخصيصه باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/create-chart-using-shape/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.

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
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### مثال على التعليمات البرمجية المصدر لإنشاء مخطط باستخدام الشكل باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
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

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة ، يمكنك إدراج شكل مخطط وتكوينه وتخصيص مظهره وحفظ المستند. يوفر Aspose.Words for .NET مجموعة شاملة من الميزات لمعالجة الكلمات باستخدام مستندات Word والرسوم البيانية ، مما يتيح لك إنشاء مخططات ذات مظهر احترافي وجذابة بشكل مباشر في تطبيقات .NET الخاصة بك.

### أسئلة وأجوبة

#### س 1. هل يمكنني إنشاء مخططات في مستند Word باستخدام Aspose.Words for .NET؟
نعم ، باستخدام Aspose.Words for .NET ، يمكنك إنشاء مخططات في مستند Word برمجيًا. يوفر Aspose.Words واجهات برمجة تطبيقات ووظائف لإدراج أنواع مختلفة من المخططات ، وتخصيص مظهرها ، ومعالجة بيانات المخطط.

#### س 2. ما أنواع المخططات التي يدعمها Aspose.Words for .NET؟
يدعم Aspose.Words for .NET مجموعة كبيرة من أنواع المخططات ، بما في ذلك المخططات الخطية ، المخططات الشريطية ، المخططات الدائرية ، المخططات المساحية ، المخططات المبعثرة ، والمزيد. يمكنك اختيار نوع الرسم البياني المناسب بناءً على بياناتك ومتطلبات التصور.

#### س 3. هل يمكنني تخصيص مظهر المخطط الذي تم إنشاؤه؟
نعم ، يمكنك تخصيص مظهر الرسم البياني الذي تم إنشاؤه باستخدام Aspose.Words for .NET. يمكنك تعديل الخصائص مثل عنوان المخطط وموضع وسيلة الإيضاح وتسميات البيانات وتسميات المحور والألوان والعناصر المرئية الأخرى لتلبية احتياجات التصميم والتنسيق الخاصة بك.
