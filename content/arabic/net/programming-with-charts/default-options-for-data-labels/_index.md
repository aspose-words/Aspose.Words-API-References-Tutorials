---
title: قم بتعيين الخيارات الافتراضية لتسميات البيانات في المخطط
linktitle: قم بتعيين الخيارات الافتراضية لتسميات البيانات في المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/default-options-for-data-labels/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين الخيارات الافتراضية لتسميات البيانات في المخطط. يوضح الكود المقدم كيفية إنشاء مخطط وإضافة سلسلة بيانات وتخصيص تسميات البيانات باستخدام Aspose.Words.

## الخطوة 1: إعداد المشروع

قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستند الإخراج.

## الخطوة 2: إنشاء مستند جديد وإدراج مخطط

 أولا، دعونا إنشاء جديد`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك، نقوم بإدراج مخطط في المستند باستخدام الملف`InsertChart` طريقة`DocumentBuilder`. في هذا المثال، سنقوم بإدراج مخطط دائري.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: إضافة سلسلة بيانات إلى المخطط

الآن، دعونا نضيف سلسلة بيانات إلى المخطط. في هذا المثال، سنضيف ثلاث فئات والقيم المقابلة لها.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## الخطوة 4: تخصيص تسميات البيانات

 لتخصيص تسميات البيانات في المخطط، نحتاج إلى الوصول إلى`ChartDataLabelCollection` الكائن المرتبط بالسلسلة.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 يمكننا بعد ذلك تعديل الخصائص المختلفة للملف`labels`كائن لتعيين الخيارات المطلوبة لتسميات البيانات. في هذا المثال، سنقوم بتمكين إظهار النسبة المئوية والقيمة، وتعطيل الخطوط السابقة، وتعيين فاصل مخصص.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## الخطوة 5: احفظ المستند

 وأخيرًا، نقوم بحفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

يكمل هذا تنفيذ تحديد الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر للخيارات الافتراضية لتسميات البيانات باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، تعلمت كيفية تعيين الخيارات الافتراضية لتسميات البيانات في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة، يمكنك إنشاء مخطط وإضافة سلسلة بيانات وتخصيص تسميات البيانات لتلبية متطلباتك المحددة. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام المخططات في مستندات Word، مما يسمح لك بمعالجة عناصر المخطط المختلفة وتحقيق المظهر والوظيفة المطلوبة.

 من خلال تحديد خصائص`ChartDataLabelCollection`الكائن المرتبط بسلسلة المخططات، يمكنك التحكم في عرض تسميات البيانات، بما في ذلك خيارات مثل إظهار النسب المئوية والقيم والخطوط السابقة والفواصل المخصصة. تمكنك هذه المرونة من تقديم البيانات بشكل فعال وتحسين التمثيل المرئي لمخططاتك.

### الأسئلة الشائعة

#### س1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة تمكن المطورين من إنشاء مستندات Word ومعالجتها وحفظها برمجيًا باستخدام تطبيقات .NET. فهو يوفر مجموعة واسعة من الميزات لمعالجة الكلمات مع عناصر المستند، بما في ذلك المخططات.

#### س2. كيف يمكنني تثبيت Aspose.Words لـ .NET؟
يمكنك تثبيت Aspose.Words لـ .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س3. هل يمكنني تخصيص جوانب أخرى من المخطط باستخدام Aspose.Words لـ .NET؟
نعم، يسمح لك Aspose.Words for .NET بتخصيص جوانب مختلفة من المخطط، مثل نوع المخطط وتسميات المحاور ووسيلة الإيضاح ومنطقة الرسم والمزيد. يمكنك الوصول إلى الخصائص المختلفة لكائن المخطط وتعديلها لتحقيق المظهر والسلوك المطلوبين.

#### س 4. هل يمكنني حفظ المخطط بتنسيقات مختلفة؟
 نعم، يدعم Aspose.Words for .NET حفظ المستند الذي يحتوي على المخطط بتنسيقات مختلفة، بما في ذلك DOCX وPDF وHTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام`Save` طريقة`Document` كائن لحفظ المستند.

#### س5. هل يمكنني تطبيق هذه التقنيات على أنواع المخططات الأخرى؟
نعم، يمكن تطبيق التقنيات الموضحة في هذا البرنامج التعليمي على أنواع المخططات الأخرى التي يدعمها Aspose.Words لـ .NET. المفتاح هو الوصول إلى الكائنات والخصائص ذات الصلة الخاصة بنوع المخطط الذي تستخدمه في معالجة الكلمات.