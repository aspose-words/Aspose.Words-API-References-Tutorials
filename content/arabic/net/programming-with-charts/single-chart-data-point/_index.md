---
title: تخصيص نقطة بيانات مخطط واحد في المخطط
linktitle: تخصيص نقطة بيانات مخطط واحد في المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تخصيص نقاط بيانات المخطط الفردي باستخدام Aspose.Words for .NET في دليل مفصل خطوة بخطوة. قم بتحسين مخططاتك باستخدام علامات وأحجام فريدة.
type: docs
weight: 10
url: /ar/net/programming-with-charts/single-chart-data-point/
---
## مقدمة

هل تساءلت يومًا كيف يمكنك إظهار مخططاتك بنقاط بيانات فريدة؟ حسنًا، اليوم هو يومك المحظوظ! نحن نتعمق في تخصيص نقطة بيانات مخطط واحدة باستخدام Aspose.Words لـ .NET. استعد للانطلاق في رحلة من خلال برنامج تعليمي خطوة بخطوة، وهو ليس مفيدًا فحسب، بل أيضًا ممتعًا وسهل المتابعة.

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من حصولك على جميع الأساسيات:

-  Aspose.Words لمكتبة .NET: تأكد من أن لديك الإصدار الأحدث.[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
- .NET Framework: تأكد من تثبيت .NET Framework على جهازك.
- الفهم الأساسي لـ C#: سيكون الفهم الأساسي لبرمجة C# مفيدًا.
- بيئة التطوير المتكاملة (IDE): يوصى باستخدام Visual Studio.

## استيراد مساحات الأسماء

أول الأشياء أولاً، فلنستورد مساحات الأسماء الضرورية للبدء في العمل:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## الخطوة 1: تهيئة المستند وDocumentBuilder

حسنًا، لنبدأ الأمور بتهيئة مستند جديد وDocumentBuilder. ستكون هذه هي اللوحة القماشية لمخططنا.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 هنا،`dataDir` هو مسار الدليل الذي ستحفظ فيه مستندك. ال`DocumentBuilder` يساعد الفصل في إنشاء المستند.

## الخطوة 2: أدخل مخططًا

بعد ذلك، دعونا نقوم بإدراج مخطط خطي في المستند. سيكون هذا ملعبنا لتخصيص نقاط البيانات.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 ال`InsertChart` تأخذ الطريقة نوع المخطط والعرض والارتفاع كمعلمات. في هذه الحالة، نقوم بإدخال مخطط خطي بعرض 432 وارتفاع 252.

## الخطوة 3: الوصول إلى سلسلة المخططات

الآن، حان الوقت للوصول إلى السلسلة الموجودة في مخططنا. يمكن أن يحتوي المخطط على سلاسل متعددة، وتحتوي كل سلسلة على نقاط بيانات.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

نحن هنا نصل إلى أول سلسلتين في مخططنا. 

## الخطوة 4: تخصيص نقاط البيانات

هنا يحدث السحر! دعونا نخصص نقاط بيانات محددة ضمن سلسلتنا.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

نحن نقوم بإحضار نقاط البيانات من السلسلة الأولى. الآن، دعونا تخصيص هذه النقاط.

### تخصيص نقطة البيانات 00

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 ل`dataPoint00`، نقوم بتعيين انفجار (مفيد للمخططات الدائرية)، وتغيير رمز العلامة إلى دائرة، وتعيين حجم العلامة إلى 15.

### تخصيص نقطة البيانات 01

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 ل`dataPoint01`، نقوم بتغيير رمز العلامة إلى معين ونضبط حجم العلامة على 20.

### تخصيص نقطة البيانات في السلسلة 1

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 بالنسبة لنقطة البيانات الثالثة في`series1`، فإننا نضبطها على العكس إذا كانت القيمة سالبة، ونغير رمز العلامة إلى نجمة، ونضبط حجم العلامة على 20.

## الخطوة 5: احفظ المستند

وأخيرًا، دعونا نحفظ مستندنا بكل التخصيصات.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 يحفظ هذا السطر المستند في الدليل المحدد بالاسم`WorkingWithCharts.SingleChartDataPoint.docx`.

## خاتمة

وهنا لديك! لقد نجحت في تخصيص نقاط بيانات فردية في مخطط باستخدام Aspose.Words for .NET. من خلال تعديل بعض الخصائص، يمكنك جعل مخططاتك أكثر إفادة وجاذبية من الناحية البصرية. لذا، تابع وجرب علامات وأحجام مختلفة لمعرفة ما هو الأفضل لبياناتك.

## الأسئلة الشائعة

### هل يمكنني تخصيص نقاط البيانات في أنواع أخرى من المخططات؟

قطعاً! يمكنك تخصيص نقاط البيانات في أنواع مختلفة من المخططات، بما في ذلك المخططات الشريطية والمخططات الدائرية والمزيد. العملية متشابهة عبر أنواع المخططات المختلفة.

### هل من الممكن إضافة تسميات مخصصة لنقاط البيانات؟

 نعم، يمكنك إضافة تسميات مخصصة إلى نقاط البيانات باستخدام`ChartDataPoint.Label` ملكية. يتيح لك ذلك توفير المزيد من السياق لكل نقطة بيانات.

### كيف يمكنني إزالة نقطة بيانات من سلسلة؟

 يمكنك إزالة نقطة بيانات عن طريق ضبط رؤيتها على استخدام خاطئ`dataPoint.IsVisible = false`.

### هل يمكنني استخدام الصور كعلامات لنقاط البيانات؟

على الرغم من أن Aspose.Words لا يدعم استخدام الصور مباشرة كعلامات، يمكنك إنشاء أشكال مخصصة واستخدامها كعلامات.

### هل من الممكن تحريك نقاط البيانات في المخطط؟

لا يدعم Aspose.Words for .NET الرسوم المتحركة لنقاط بيانات المخطط. ومع ذلك، يمكنك إنشاء مخططات متحركة باستخدام أدوات أخرى وتضمينها في مستندات Word الخاصة بك.