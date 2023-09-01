---
title: تنسيق رقم تسمية البيانات في المخطط
linktitle: تنسيق رقم تسمية البيانات في المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنسيق عدد تسميات البيانات في المخطط باستخدام Aspose.Words for .NET. تخصيص تنسيقات الأرقام لتسميات البيانات بسهولة.
type: docs
weight: 10
url: /ar/net/programming-with-charts/format-number-of-data-label/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتنسيق عدد تسميات البيانات في المخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص تنسيق الأرقام لتسميات البيانات.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستند الإخراج.

## الخطوة 2: إنشاء مستند جديد وإدراج مخطط

 إنشاء جديد`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك، قم بإدراج مخطط في المستند باستخدام`InsertChart` طريقة`DocumentBuilder`. في هذا المثال، سنقوم بإدراج مخطط خطي.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## الخطوة 3: إضافة بيانات السلسلة إلى المخطط

أضف بيانات السلسلة إلى المخطط. في هذا المثال، سنضيف ثلاث فئات والقيم المقابلة لها.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## الخطوة 4: تخصيص تنسيق الأرقام لتسميات البيانات

 لتنسيق عدد تسميات البيانات، قم بالوصول إلى`DataLabels` المجموعة المرتبطة بالسلسلة.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

في هذا المثال، قمنا بتعيين تنسيقات أرقام مختلفة لكل تسمية بيانات. يتم تنسيق تسمية البيانات الأولى كعملة، والثانية كتاريخ، والثالثة كنسبة مئوية.

## الخطوة 5: احفظ المستند

 وأخيرًا، احفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

يكمل هذا تنفيذ تنسيق عدد تسميات البيانات في المخطط باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لتنسيق رقم تسمية البيانات باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// حذف السلسلة التي تم إنشاؤها افتراضيًا.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// أو يمكنك تعيين رمز التنسيق ليتم ربطه بخلية مصدر،
	// في هذه الحالة سيتم إعادة تعيين NumberFormat إلى الوضع العام ويتم توريثه من الخلية المصدر.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تنسيق عدد تسميات البيانات في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك إنشاء مخطط وإضافة بيانات متسلسلة وتخصيص تنسيق أرقام تسميات البيانات وفقًا لمتطلباتك.

 يوفر Aspose.Words for .NET واجهة برمجة تطبيقات شاملة لمعالجة الكلمات باستخدام المخططات في مستندات Word، مما يسمح لك بمعالجة الجوانب المختلفة للمخطط، بما في ذلك تسميات البيانات. من خلال الوصول إلى`DataLabels` المرتبطة بسلسلة، يمكنك تخصيص تنسيق الأرقام لتسميات البيانات الفردية.

تسمح لك واجهة برمجة التطبيقات (API) بالتحكم في عرض القيم، وتعيين تنسيقات أرقام مختلفة لكل تسمية بيانات، وربط تنسيق الأرقام بخلية مصدر. تمكنك هذه المرونة من تقديم البيانات الرقمية في المخططات بالتنسيق المطلوب، مثل رموز العملة وتنسيقات التاريخ وقيم النسبة المئوية.

باستخدام Aspose.Words for .NET، يمكنك دمج إمكانات التخطيط القوية في تطبيقات .NET الخاصة بك وإنشاء مستندات ذات مظهر احترافي باستخدام مخططات منسقة بالكامل وتسميات بيانات.

### الأسئلة الشائعة

#### س1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET عبارة عن مكتبة معالجة مستندات غنية بالميزات تمكن المطورين من إنشاء مستندات Word ومعالجتها وحفظها برمجيًا في تطبيقات .NET. فهو يوفر نطاقًا واسعًا من الميزات لمعالجة الكلمات باستخدام عناصر المستند، بما في ذلك المخططات وتسميات البيانات.

#### س2. كيف يمكنني تثبيت Aspose.Words لـ .NET؟
يمكنك تثبيت Aspose.Words لـ .NET عن طريق تنزيله باستخدام مدير الحزم NuGet في Visual Studio. ما عليك سوى البحث عن "Aspose.Words" في مدير الحزم NuGet وتثبيته في مشروعك.

#### س3. هل يمكنني تنسيق جوانب أخرى من المخطط باستخدام Aspose.Words لـ .NET؟
نعم، يوفر Aspose.Words for .NET إمكانات واسعة النطاق لتنسيق الجوانب المختلفة للمخطط. بالإضافة إلى تسميات البيانات، يمكنك تخصيص نوع المخطط وبيانات السلسلة وخصائص المحور ووسيلة الإيضاح والعنوان ومنطقة الرسم والعديد من العناصر الأخرى للمخطط. توفر واجهة برمجة التطبيقات (API) تحكمًا دقيقًا في مظهر المخطط وتنسيقه.

#### س 4. هل يمكنني تطبيق تنسيقات أرقام مختلفة على تسميات بيانات مختلفة في نفس السلسلة؟
 نعم، يسمح لك Aspose.Words for .NET بتطبيق تنسيقات أرقام مختلفة على تسميات البيانات الفردية ضمن نفس السلسلة. من خلال الوصول إلى`DataLabels` المجموعة المرتبطة بسلسلة، يمكنك تعيين`FormatCode` خاصية كل تسمية بيانات لتحديد تنسيق الرقم المطلوب. يتيح لك ذلك عرض قيم رقمية بتنسيقات مختلفة داخل نفس المخطط.

#### س5. هل يمكنني استخدام تنسيقات الأرقام المخصصة لتسميات البيانات؟
 نعم، يدعم Aspose.Words for .NET تنسيقات الأرقام المخصصة لتسميات البيانات. يمكنك تحديد تنسيق الرقم المطلوب عن طريق ضبط`FormatCode`خاصية تسمية البيانات إلى رمز تنسيق مخصص. ويمنحك هذا المرونة لتطبيق نطاق واسع من تنسيقات الأرقام، مثل رموز العملات، وتنسيقات التاريخ، وقيم النسبة المئوية، والمزيد.

#### س6. هل يمكنني حفظ المخطط مع تسميات البيانات المنسقة بتنسيقات مختلفة؟
 نعم، يسمح لك Aspose.Words for .NET بحفظ المستند الذي يحتوي على المخطط مع تسميات البيانات المنسقة بتنسيقات مختلفة، مثل DOCX وPDF وHTML والمزيد. يمكنك اختيار التنسيق المناسب بناءً على متطلباتك واستخدام`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بتسميات البيانات المنسقة في المستند المحفوظ.