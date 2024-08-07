---
title: إضافة قيم التاريخ والوقت إلى محور المخطط
linktitle: إضافة قيم التاريخ والوقت إلى محور المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words for .NET في هذا الدليل الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-charts/date-time-values-to-axis/
---
## مقدمة

يمكن أن يكون إنشاء المخططات في المستندات طريقة فعالة لتصور البيانات. عند التعامل مع بيانات السلاسل الزمنية، تعد إضافة قيم التاريخ والوقت إلى محور المخطط أمرًا بالغ الأهمية لتحقيق الوضوح. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة قيم التاريخ والوقت إلى محور المخطط باستخدام Aspose.Words for .NET. سيساعدك هذا الدليل التفصيلي خطوة بخطوة على إعداد بيئتك وكتابة التعليمات البرمجية وفهم كل جزء من العملية. دعونا الغوص في!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio أو أي برنامج .NET IDE: أنت بحاجة إلى بيئة تطوير لكتابة تعليمات NET البرمجية وتشغيلها.
2.  Aspose.Words لـ .NET: يجب أن يكون لديك Aspose.Words لمكتبة .NET مثبتة. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
3. المعرفة الأساسية بـ C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة C#.
4.  ترخيص Aspose صالح: يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

## استيراد مساحات الأسماء

للبدء، تأكد من أن لديك مساحات الأسماء الضرورية المستوردة في مشروعك. هذه الخطوة ضرورية للوصول إلى فئات وأساليب Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

أولاً، تحتاج إلى تحديد الدليل الذي سيتم حفظ المستند فيه. يعد هذا أمرًا مهمًا لتنظيم ملفاتك وضمان تشغيل التعليمات البرمجية الخاصة بك بشكل صحيح.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وDocumentBuilder

 بعد ذلك، قم بإنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` هدف. ستساعدك هذه الكائنات في إنشاء مستندك ومعالجته.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل مخططًا في المستند

 الآن، قم بإدراج مخطط في المستند الخاص بك باستخدام`DocumentBuilder` هدف. في هذا المثال، نستخدم مخططًا عموديًا، ولكن يمكنك اختيار أنواع أخرى أيضًا.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 4: مسح السلسلة الموجودة

قم بمسح أي سلسلة موجودة في المخطط للتأكد من أنك تبدأ بقائمة فارغة. هذه الخطوة ضرورية للبيانات المخصصة.

```csharp
chart.Series.Clear();
```

## الخطوة 5: إضافة قيم التاريخ والوقت إلى السلسلة

أضف قيم التاريخ والوقت إلى سلسلة المخططات. تتضمن هذه الخطوة إنشاء صفائف للتواريخ والقيم المقابلة.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## الخطوة 6: تكوين المحور السيني

قم بتعيين علامات القياس والتجزئة للمحور السيني. وهذا يضمن عرض التواريخ بشكل صحيح وعلى فترات زمنية مناسبة.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## الخطوة 7: احفظ المستند

وأخيرًا، احفظ مستندك في الدليل المحدد. تُنهي هذه الخطوة العملية، ويجب أن يحتوي مستندك الآن على مخطط بقيم التاريخ والوقت على المحور السيني.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## خاتمة

تعد إضافة قيم التاريخ والوقت إلى محور المخطط في المستند عملية مباشرة مع Aspose.Words for .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك إنشاء مخططات واضحة وغنية بالمعلومات تصور بيانات السلاسل الزمنية بشكل فعال. سواء كنت تقوم بإعداد تقارير أو عروض تقديمية أو أي مستند يتطلب تمثيل بيانات تفصيلية، فإن Aspose.Words يوفر الأدوات التي تحتاجها لتحقيق النجاح.

## الأسئلة الشائعة

### هل يمكنني استخدام أنواع مخططات أخرى مع Aspose.Words لـ .NET؟

نعم، يدعم Aspose.Words أنواعًا مختلفة من المخططات، بما في ذلك الخط والشريط والدائري والمزيد.

### كيف يمكنني تخصيص مظهر الرسم البياني الخاص بي؟

يمكنك تخصيص المظهر عن طريق الوصول إلى خصائص المخطط وإعداد الأنماط والألوان والمزيد.

### هل من الممكن إضافة سلسلة متعددة إلى الرسم البياني؟

 قطعاً! يمكنك إضافة سلاسل متعددة إلى المخطط الخاص بك عن طريق الاتصال بـ`Series.Add` طريقة عدة مرات مع بيانات مختلفة.

### ماذا لو كنت بحاجة إلى تحديث بيانات الرسم البياني ديناميكيًا؟

يمكنك تحديث بيانات المخطط ديناميكيًا عن طريق معالجة خصائص السلسلة والمحور برمجيًا بناءً على متطلباتك.

### أين يمكنني العثور على وثائق أكثر تفصيلاً حول Aspose.Words for .NET؟

 يمكنك العثور على وثائق أكثر تفصيلا[هنا](https://reference.aspose.com/words/net/).