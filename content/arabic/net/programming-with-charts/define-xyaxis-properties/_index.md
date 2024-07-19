---
title: تحديد خصائص المحور XY في الرسم البياني
linktitle: تحديد خصائص المحور XY في الرسم البياني
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد خصائص المحور XY في المخطط باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة. مثالي لمطوري .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/define-xyaxis-properties/
---
## مقدمة

الرسوم البيانية هي أداة قوية لتصور البيانات. عندما تحتاج إلى إنشاء مستندات احترافية باستخدام مخططات ديناميكية، فإن Aspose.Words for .NET هي مكتبة لا تقدر بثمن. سترشدك هذه المقالة خلال عملية تحديد خصائص محور XY في مخطط باستخدام Aspose.Words for .NET، مع تفصيل كل خطوة لضمان الوضوح وسهولة الفهم.

## المتطلبات الأساسية

قبل الغوص في عالم البرمجة، هناك بعض المتطلبات الأساسية التي يجب عليك توفرها:

1. Aspose.Words for .NET: تأكد من أن لديك مكتبة Aspose.Words for .NET. أنت تستطيع[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: أنت بحاجة إلى بيئة تطوير متكاملة (IDE) مثل Visual Studio.
3. .NET Framework: تأكد من إعداد بيئة التطوير لديك لتطوير .NET.
4. المعرفة الأساسية بـ C#: يفترض هذا الدليل أن لديك فهمًا أساسيًا لبرمجة C#.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروعك. يضمن ذلك إمكانية الوصول إلى جميع الفئات والأساليب المطلوبة لإنشاء المستندات والمخططات ومعالجتها.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

سنقوم بتقسيم العملية إلى خطوات بسيطة، تركز كل منها على جزء معين من تحديد خصائص المحور XY في المخطط.

## الخطوة 1: تهيئة المستند وDocumentBuilder

 أولاً، تحتاج إلى تهيئة مستند جديد و`DocumentBuilder` هدف. ال`DocumentBuilder` يساعد في إدراج المحتوى في المستند.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل مخططًا

بعد ذلك، ستقوم بإدراج مخطط في المستند. في هذا المثال، سنستخدم مخططًا مساحيًا. يمكنك تخصيص أبعاد المخطط حسب الحاجة.

```csharp
// إدراج الرسم البياني
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: مسح السلسلة الافتراضية وإضافة بيانات مخصصة

بشكل افتراضي، سيحتوي المخطط على بعض السلاسل المحددة مسبقًا. سنقوم بمسحها وإضافة سلسلة البيانات المخصصة لدينا.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## الخطوة 4: تحديد خصائص المحور X

حان الوقت الآن لتحديد خصائص المحور X. يتضمن ذلك تعيين نوع الفئة وتخصيص تقاطع المحور وضبط علامات التجزئة والتسميات.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //تقاس بوحدات العرض للمحور Y (المئات).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## الخطوة 5: تحديد خصائص المحور Y

وبالمثل، سوف تقوم بتعيين خصائص المحور Y. يتضمن ذلك تعيين موضع علامة التجزئة والوحدات الرئيسية والثانوية ووحدة العرض والقياس.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## الخطوة 6: احفظ المستند

وأخيرًا، احفظ المستند في الدليل المحدد. سيؤدي هذا إلى إنشاء مستند Word مع المخطط المخصص.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## خاتمة

يعد إنشاء المخططات وتخصيصها في مستندات Word باستخدام Aspose.Words for .NET أمرًا سهلاً بمجرد فهم الخطوات المتضمنة. يرشدك هذا الدليل خلال عملية تحديد خصائص المحور XY في المخطط، بدءًا من تهيئة المستند وحتى حفظ المنتج النهائي. باستخدام هذه المهارات، يمكنك إنشاء مخططات تفصيلية ذات مظهر احترافي تعمل على تحسين مستنداتك.

## الأسئلة الشائعة

### ما أنواع المخططات التي يمكنني إنشاؤها باستخدام Aspose.Words لـ .NET؟
يمكنك إنشاء أنواع مختلفة من المخططات، بما في ذلك المساحة والشريط والخط والدائري والمزيد.

### كيف أقوم بتثبيت Aspose.Words لـ .NET؟
 يمكنك تنزيل Aspose.Words لـ .NET من[هنا](https://releases.aspose.com/words/net/) واتبع تعليمات التثبيت المقدمة.

### هل يمكنني تخصيص مظهر مخططاتي؟
نعم، يسمح Aspose.Words for .NET بالتخصيص الشامل للمخططات، بما في ذلك الألوان والخطوط وخصائص المحاور.

### هل تتوفر نسخة تجريبية مجانية من Aspose.Words لـ .NET؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على المزيد من البرامج التعليمية والوثائق؟
 يمكنك العثور على المزيد من البرامج التعليمية والوثائق التفصيلية على[Aspose.Words لصفحة وثائق .NET](https://reference.aspose.com/words/net/).
