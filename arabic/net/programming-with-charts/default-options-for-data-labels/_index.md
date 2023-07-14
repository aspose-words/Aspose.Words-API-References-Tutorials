---
title: قم بتعيين الخيارات الافتراضية لتسميات البيانات في مخطط
linktitle: قم بتعيين الخيارات الافتراضية لتسميات البيانات في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعيين الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/default-options-for-data-labels/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين الخيارات الافتراضية لتسميات البيانات في الرسم البياني. يوضح الكود المقدم كيفية إنشاء مخطط وإضافة سلسلة بيانات وتخصيص تسميات البيانات باستخدام Aspose.Words.

## الخطوة 1: قم بإعداد المشروع

قبل أن نبدأ ، تأكد من توفر المتطلبات التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير حزمة NuGet لتثبيته.
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

 يمكننا بعد ذلك تعديل الخصائص المختلفة لملف`labels`لتعيين الخيارات المطلوبة لتسميات البيانات. في هذا المثال ، سنقوم بتمكين عرض النسبة المئوية والقيمة ، وتعطيل الخطوط البادئة ، وتعيين فاصل مخصص.

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
	//المسار إلى دليل المستند الخاص بك
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تعيين الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إنشاء مخطط وإضافة سلسلة بيانات وتخصيص تسميات البيانات لتلبية متطلباتك المحددة. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع مخططات في مستندات Word ، مما يسمح لك بمعالجة عناصر المخططات المختلفة وتحقيق المظهر والوظائف المطلوبة.

 من خلال تحديد خصائص ملف`ChartDataLabelCollection`كائن مرتبط بسلسلة المخطط ، يمكنك التحكم في عرض تسميات البيانات ، بما في ذلك الخيارات مثل إظهار النسب المئوية والقيم وخطوط البادئة والفواصل المخصصة. تتيح لك هذه المرونة تقديم البيانات بشكل فعال وتحسين التمثيل المرئي لمخططاتك.

### أسئلة وأجوبة

#### س 1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة تمكن المطورين من إنشاء مستندات Word ومعالجتها وحفظها برمجيًا باستخدام تطبيقات .NET. يوفر مجموعة كبيرة من الميزات لمعالجة الكلمات مع عناصر المستند ، بما في ذلك المخططات.

#### س 2. كيف يمكنني تثبيت Aspose.Words for .NET؟
يمكنك تثبيت Aspose.Words for .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س 3. هل يمكنني تخصيص جوانب أخرى من المخطط باستخدام Aspose.Words for .NET؟
نعم ، يسمح لك Aspose.Words for .NET بتخصيص جوانب مختلفة من المخطط ، مثل نوع المخطط ، تسميات المحور ، وسيلة الإيضاح ، منطقة الرسم ، والمزيد. يمكنك الوصول إلى الخصائص المختلفة لكائن المخطط وتعديلها لتحقيق المظهر والسلوك المطلوبين.

#### س 4. هل يمكنني حفظ الرسم البياني بتنسيقات مختلفة؟
 نعم ، يدعم Aspose.Words for .NET حفظ المستند الذي يحتوي على الرسم البياني بتنسيقات مختلفة ، بما في ذلك DOCX و PDF و HTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند.

#### س 5. هل يمكنني تطبيق هذه الأساليب على أنواع الرسوم البيانية الأخرى؟
نعم ، يمكن تطبيق الأساليب الموضحة في هذا البرنامج التعليمي على أنواع المخططات الأخرى التي يدعمها Aspose.Words for .NET. المفتاح هو الوصول إلى الكائنات والخصائص ذات الصلة الخاصة بنوع المخطط الذي تستخدمه في معالجة الكلمات.