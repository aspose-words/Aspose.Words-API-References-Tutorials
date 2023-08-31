---
title: إنشاء وتخصيص الرسم البياني باستخدام الشكل
linktitle: إنشاء وتخصيص الرسم البياني باستخدام الشكل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء مخطط وتخصيصه باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/create-chart-using-shape/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words لـ .NET.

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

## الخطوة 3: إدراج شكل مخطط وتكوينه
 قم بإدراج شكل مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder` هدف. قم بتعيين نوع المخطط والأبعاد المطلوبة.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: تخصيص المخطط
قم بتخصيص المخطط عن طريق تعديل خصائص مختلفة مثل عنوان المخطط ووسيلة الإيضاح.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### مثال على التعليمات البرمجية المصدر لإنشاء مخطط باستخدام الشكل باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// يرجى ملاحظة أنه إذا تم تحديد قيمة فارغة أو فارغة كنص عنوان، فسيتم عرض العنوان الذي تم إنشاؤه تلقائيًا.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

هذا كل شيء! لقد نجحت في إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words لـ .NET.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط باستخدام شكل في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك إدراج شكل مخطط وتكوينه وتخصيص مظهره وحفظ المستند. يوفر Aspose.Words for .NET مجموعة شاملة من الميزات لمعالجة الكلمات باستخدام مستندات ومخططات Word، مما يتيح لك إنشاء مخططات ذات مظهر احترافي وجذابة بصريًا مباشرة في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س1. هل يمكنني إنشاء مخططات في مستند Word باستخدام Aspose.Words لـ .NET؟
نعم، باستخدام Aspose.Words for .NET، يمكنك إنشاء مخططات في مستند Word برمجيًا. يوفر Aspose.Words واجهات برمجة التطبيقات والوظائف لإدراج أنواع مختلفة من المخططات وتخصيص مظهرها ومعالجة بيانات المخطط.

#### س2. ما أنواع المخططات التي يدعمها Aspose.Words لـ .NET؟
يدعم Aspose.Words for .NET نطاقًا واسعًا من أنواع المخططات، بما في ذلك المخططات الخطية والمخططات الشريطية والمخططات الدائرية والمخططات المساحية والمخططات المبعثرة والمزيد. يمكنك اختيار نوع المخطط المناسب بناءً على متطلبات البيانات والمرئيات الخاصة بك.

#### س3. هل يمكنني تخصيص مظهر المخطط الذي تم إنشاؤه؟
نعم، يمكنك تخصيص مظهر المخطط الذي تم إنشاؤه باستخدام Aspose.Words for .NET. يمكنك تعديل خصائص مثل عنوان المخطط وموضع وسيلة الإيضاح وتسميات البيانات وتسميات المحاور والألوان والعناصر المرئية الأخرى لتلبية احتياجاتك الخاصة في التصميم والتنسيق.
