---
title: إدراج مخطط عمودي بسيط في مستند Word
linktitle: إدراج مخطط عمودي بسيط في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج مخطط عمودي بسيط في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-simple-column-chart/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words لـ .NET لإدراج مخطط عمودي بسيط في المستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وحفظ المستند.

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

 بعد ذلك، استخدم`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط عمودي في المستند. يمكنك تحديد أنواع وأحجام مختلفة للمخططات وفقًا لمتطلباتك.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: إضافة بيانات السلسلة إلى المخطط

إضافة بيانات السلسلة إلى المخطط. في هذا المثال، سنقوم بإضافة سلسلة متعددة تحتوي كل منها على فئتين.

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

 وأخيرًا، احفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

يكمل هذا تنفيذ إدراج مخطط عمودي بسيط باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإدراج مخطط عمودي بسيط باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// يمكنك تحديد أنواع وأحجام مختلفة للمخططات.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// حذف السلسلة التي تم إنشاؤها افتراضيًا.
	seriesColl.Clear();
	// قم بإنشاء مصفوفة أسماء الفئات، في هذا البرنامج التعليمي لدينا فئتان.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// يرجى ملاحظة أن صفائف البيانات يجب ألا تكون فارغة ويجب أن تكون المصفوفات بنفس الحجم.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إدراج مخطط عمودي بسيط في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك إنشاء مستند جديد وإدراج مخطط عمودي وإضافة سلاسل متعددة مع الفئات والقيم المقابلة وحفظ المستند بالمخطط.

يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام المخططات في مستندات Word. يعد المخطط العمودي البسيط وسيلة فعالة لتمثيل البيانات ومقارنتها في فئات مختلفة. باستخدام Aspose.Words for .NET، يمكنك بسهولة إنشاء مخططات عمودية تحتوي على بيانات مخصصة، وإضافة سلاسل متعددة للمقارنة المرئية، وتخصيص مظهر المخطط وفقًا لمتطلباتك.

باستخدام Aspose.Words for .NET، يمكنك أتمتة عملية إنشاء المستندات باستخدام المخططات العمودية، مما يوفر الوقت والجهد في إنشاء المستندات يدويًا. توفر المكتبة نطاقًا واسعًا من أنواع المخططات، بما في ذلك المخططات العمودية البسيطة، وتوفر خيارات تخصيص متنوعة لتخصيص مظهر المخطط ليناسب احتياجاتك.

### الأسئلة الشائعة

#### س1. ما هو المخطط العمودي؟
المخطط العمودي هو نوع من المخططات التي تعرض البيانات باستخدام أشرطة عمودية ذات ارتفاعات مختلفة. يمثل كل عمود فئة، ويتوافق ارتفاع العمود مع قيمة تلك الفئة. تُستخدم المخططات العمودية بشكل شائع لمقارنة البيانات عبر فئات مختلفة أو لتتبع التغييرات بمرور الوقت.

#### س2. هل يمكنني إضافة سلاسل متعددة إلى المخطط العمودي؟
نعم، باستخدام Aspose.Words for .NET، يمكنك إضافة سلاسل متعددة إلى المخطط العمودي. تمثل كل سلسلة مجموعة من نقاط البيانات مع فئاتها وقيمها. من خلال إضافة سلاسل متعددة، يمكنك مقارنة مجموعات البيانات المختلفة وتحليلها ضمن نفس المخطط العمودي، مما يوفر عرضًا شاملاً لبياناتك.

#### س3. هل يمكنني تخصيص مظهر المخطط العمودي؟
نعم، يسمح لك Aspose.Words for .NET بتخصيص الجوانب المختلفة لمظهر المخطط العمودي. يمكنك تعديل خصائص مثل لون السلسلة وتسميات المحاور وتسميات البيانات وتنسيق منطقة المخطط. توفر المكتبة مجموعة غنية من واجهات برمجة التطبيقات للتحكم في العناصر المرئية للمخطط وإنشاء مظهر مخصص يناسب احتياجاتك.

#### س 4. هل يمكنني حفظ المستند مع المخطط العمودي المدرج بتنسيقات مختلفة؟
 نعم، يسمح لك Aspose.Words for .NET بحفظ المستند مع المخطط العمودي المدرج بتنسيقات مختلفة، مثل DOCX وPDF وHTML والمزيد. يمكنك اختيار تنسيق الإخراج المطلوب بناءً على متطلباتك واستخدام`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بالمخطط العمودي المدرج في المستند المحفوظ.

#### س5. هل يمكنني تعديل بيانات ومظهر المخطط العمودي بعد إدراجه؟
نعم، بعد إدراج المخطط العمودي في المستند، يمكنك تعديل بياناته ومظهره باستخدام واجهات برمجة التطبيقات التي يوفرها Aspose.Words لـ .NET. يمكنك تحديث بيانات السلسلة بفئات وقيم جديدة، وتغيير ألوان الأعمدة وتنسيقها، وتخصيص خصائص المحور، وتطبيق خيارات التنسيق المتنوعة لإنشاء مخططات ديناميكية وجذابة بصريًا في مستندات Word الخاصة بك.