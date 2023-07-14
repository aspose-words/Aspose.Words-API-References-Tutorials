---
title: تنسيق رقم تسمية البيانات في مخطط
linktitle: تنسيق رقم تسمية البيانات في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET. تخصيص تنسيقات الأرقام لتسميات البيانات بسهولة.
type: docs
weight: 10
url: /ar/net/programming-with-charts/format-number-of-data-label/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتنسيق عدد تسميات البيانات في مخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص تنسيق الأرقام لتسميات البيانات.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستند الناتج.

## الخطوة 2: أنشئ مستندًا جديدًا وأدخل مخططًا

 إنشاء ملف`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك ، أدخل مخططًا في المستند باستخدام ملف`InsertChart` طريقة`DocumentBuilder`. في هذا المثال ، سنقوم بإدراج مخطط خطي.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف ثلاث فئات والقيم المقابلة لها.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## الخطوة 4: تخصيص تنسيق الأرقام لتسميات البيانات

 لتنسيق عدد تسميات البيانات ، قم بالوصول إلى`DataLabels` المجموعة المرتبطة بالسلسلة.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

في هذا المثال ، قمنا بتعيين تنسيقات أرقام مختلفة لكل تسمية بيانات. تم تنسيق تسمية البيانات الأولى كعملة ، والثانية كتاريخ ، والثالثة كنسبة مئوية.

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

هذا يكمل تنفيذ تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لتنسيق رقم تسمية البيانات باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// حذف السلاسل التي تم إنشاؤها بشكل افتراضي.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// أو يمكنك تعيين كود التنسيق لربطه بخلية مصدر ،
	// في هذه الحالة ، سيتم إعادة تعيين NumberFormat إلى عام وسيتم توريثه من خلية مصدر.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مخطط وإضافة بيانات سلسلة وتخصيص تنسيق الأرقام لتسميات البيانات وفقًا لمتطلباتك.

 يوفر Aspose.Words for .NET واجهة برمجة تطبيقات شاملة لمعالجة الكلمات مع مخططات في مستندات Word ، مما يسمح لك بمعالجة الجوانب المختلفة للمخطط ، بما في ذلك تسميات البيانات. من خلال الوصول إلى`DataLabels` المجموعة المرتبطة بسلسلة ، يمكنك تخصيص تنسيق الأرقام لتسميات البيانات الفردية.

تتيح لك واجهة برمجة التطبيقات التحكم في عرض القيم وتعيين تنسيقات أرقام مختلفة لكل تسمية بيانات وربط تنسيق الأرقام بخلية مصدر. تتيح لك هذه المرونة تقديم البيانات الرقمية في المخططات بالتنسيق المطلوب ، مثل رموز العملات وتنسيقات التاريخ وقيم النسبة المئوية.

باستخدام Aspose.Words for .NET ، يمكنك دمج إمكانات الرسوم البيانية القوية في تطبيقات .NET الخاصة بك وإنشاء مستندات ذات مظهر احترافي مع مخططات وتسميات بيانات منسقة بالكامل.

### أسئلة وأجوبة

#### س 1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة معالجة مستندات غنية بالمميزات تتيح للمطورين إنشاء مستندات Word ومعالجتها وحفظها برمجيًا في تطبيقات .NET. يوفر مجموعة كبيرة من الميزات لمعالجة الكلمات مع عناصر المستند ، بما في ذلك المخططات وتسميات البيانات.

#### س 2. كيف يمكنني تثبيت Aspose.Words for .NET؟
يمكنك تثبيت Aspose.Words for .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س 3. هل يمكنني تنسيق جوانب أخرى من المخطط باستخدام Aspose.Words for .NET؟
نعم ، يوفر Aspose.Words for .NET إمكانيات واسعة لتنسيق الجوانب المختلفة للمخطط. بالإضافة إلى تسميات البيانات ، يمكنك تخصيص نوع المخطط وبيانات السلسلة وخصائص المحور ووسيلة الإيضاح والعنوان ومنطقة الرسم والعديد من العناصر الأخرى في المخطط. توفر واجهة برمجة التطبيقات تحكمًا دقيقًا في مظهر المخطط وتنسيقه.

#### س 4. هل يمكنني تطبيق تنسيقات أرقام مختلفة على تسميات بيانات مختلفة في نفس السلسلة؟
 نعم ، يسمح لك Aspose.Words for .NET بتطبيق تنسيقات أرقام مختلفة على تسميات البيانات الفردية ضمن نفس السلسلة. من خلال الوصول إلى`DataLabels` المجموعة المرتبطة بسلسلة ، يمكنك تعيين`FormatCode` خاصية كل تسمية بيانات لتحديد تنسيق الرقم المطلوب. يتيح لك ذلك تقديم قيم رقمية بتنسيقات مختلفة داخل نفس الرسم البياني.

#### س 5. هل يمكنني استخدام تنسيقات الأرقام المخصصة لتسميات البيانات؟
 نعم ، يدعم Aspose.Words for .NET تنسيقات الأرقام المخصصة لتسميات البيانات. يمكنك تحديد تنسيق الرقم المطلوب عن طريق ضبط`FormatCode`خاصية تسمية البيانات إلى رمز تنسيق مخصص. يمنحك هذا المرونة لتطبيق مجموعة كبيرة من تنسيقات الأرقام ، مثل رموز العملات وتنسيقات التاريخ وقيم النسبة المئوية والمزيد.

#### س 6. هل يمكنني حفظ المخطط مع تسميات البيانات المنسقة بتنسيقات مختلفة؟
 نعم ، يتيح لك Aspose.Words for .NET حفظ المستند الذي يحتوي على مخطط مع تسميات بيانات منسقة بتنسيقات مختلفة ، مثل DOCX و PDF و HTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بتسميات البيانات المنسقة في المستند المحفوظ.