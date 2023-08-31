---
title: إدراج مخطط عمودي بسيط في مستند Word
linktitle: إدراج مخطط عمودي بسيط في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج مخطط عمودي بسيط في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-simple-column-chart/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإدراج مخطط عمودي بسيط في مستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وحفظ المستند.

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

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط عمودي في المستند. يمكنك تحديد أنواع وأحجام مخططات مختلفة حسب متطلباتك.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف سلاسل متعددة بفئتين لكل منهما.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

هذا يكمل تنفيذ إدراج مخطط عمودي بسيط باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإدراج مخطط عمودي بسيط باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// يمكنك تحديد أنواع وأحجام مخططات مختلفة.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// حذف السلاسل التي تم إنشاؤها بشكل افتراضي.
	seriesColl.Clear();
	// قم بإنشاء مصفوفة أسماء الفئات ، في هذا البرنامج التعليمي لدينا فئتان.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// الرجاء ملاحظة أنه يجب ألا تكون صفائف البيانات فارغة ويجب أن تكون المصفوفات بنفس الحجم.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إدراج مخطط عمودي بسيط في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد ، وإدراج مخطط عمودي ، وإضافة سلاسل متعددة بالفئات والقيم المقابلة ، وحفظ المستند مع المخطط.

يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات مع مخططات في مستندات Word. يعد مخطط العمود البسيط طريقة فعالة لتمثيل ومقارنة البيانات في فئات مختلفة. باستخدام Aspose.Words for .NET ، يمكنك بسهولة إنشاء مخططات عمودية ببيانات مخصصة وإضافة سلاسل متعددة للمقارنة المرئية وتخصيص مظهر المخطط وفقًا لمتطلباتك.

باستخدام Aspose.Words for .NET ، يمكنك أتمتة عملية إنشاء المستندات باستخدام مخططات عمودية ، مما يوفر الوقت والجهد في إنشاء المستندات يدويًا. تقدم المكتبة مجموعة واسعة من أنواع المخططات ، بما في ذلك المخططات العمودية البسيطة ، وتوفر خيارات تخصيص متنوعة لتخصيص مظهر المخطط ليناسب احتياجاتك.

### أسئلة وأجوبة

#### س 1. ما هو مخطط العمود؟
المخطط العمودي هو نوع من المخططات التي تعرض البيانات باستخدام أشرطة عمودية ذات ارتفاعات مختلفة. يمثل كل عمود فئة ، ويتوافق ارتفاع العمود مع قيمة تلك الفئة. تُستخدم المخططات العمودية بشكل شائع لمقارنة البيانات عبر فئات مختلفة أو لتعقب التغييرات بمرور الوقت.

#### س 2. هل يمكنني إضافة سلاسل متعددة إلى مخطط العمود؟
نعم ، باستخدام Aspose.Words for .NET ، يمكنك إضافة سلاسل متعددة إلى مخطط العمود. تمثل كل سلسلة مجموعة من نقاط البيانات مع فئاتها وقيمها. من خلال إضافة سلاسل متعددة ، يمكنك مقارنة مجموعات البيانات المختلفة وتحليلها داخل مخطط العمود نفسه ، مما يوفر عرضًا شاملاً لبياناتك.

#### س 3. هل يمكنني تخصيص مظهر المخطط العمودي؟
نعم ، يسمح لك Aspose.Words for .NET بتخصيص جوانب مختلفة من مظهر مخطط العمود. يمكنك تعديل الخصائص مثل لون السلسلة وتسميات المحور وتسميات البيانات وتنسيق منطقة المخطط. توفر المكتبة مجموعة غنية من واجهات برمجة التطبيقات للتحكم في العناصر المرئية للمخطط وإنشاء مظهر مخصص يناسب احتياجاتك.

#### س 4. هل يمكنني حفظ المستند مع الرسم البياني العمودي المدرج بتنسيقات مختلفة؟
 نعم ، يسمح لك Aspose.Words for .NET بحفظ المستند مع الرسم البياني العمودي المدرج بتنسيقات مختلفة ، مثل DOCX و PDF و HTML والمزيد. يمكنك اختيار تنسيق الإخراج المطلوب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بالتخطيط العمودي المدرج في المستند المحفوظ.

#### س 5. هل يمكنني تعديل بيانات ومظهر مخطط العمود بعد إدراجه؟
نعم ، بعد إدراج مخطط العمود في المستند ، يمكنك تعديل بياناته ومظهره باستخدام واجهات برمجة التطبيقات التي توفرها Aspose.Words for .NET. يمكنك تحديث بيانات السلسلة بفئات وقيم جديدة ، وتغيير الألوان وتنسيق الأعمدة ، وتخصيص خصائص المحور ، وتطبيق خيارات التنسيق المختلفة لإنشاء مخططات ديناميكية وجذابة بصريًا في مستندات Word الخاصة بك.