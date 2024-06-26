---
title: إدراج مخطط مساحي في مستند Word
linktitle: إدراج مخطط مساحي في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج مخطط مساحي في مستند باستخدام Aspose.Words لـ .NET. أضف بيانات السلسلة واحفظ المستند مع المخطط.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-area-chart/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words لـ .NET لإدراج مخطط مساحي في مستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وحفظ المستند.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستند الإخراج.

## الخطوة 2: إنشاء مستند جديد وإدراج مخطط.

 إنشاء جديد`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك، استخدم`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط مساحي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: إضافة بيانات السلسلة إلى المخطط

إضافة بيانات السلسلة إلى المخطط. في هذا المثال، سنضيف خمس نقاط بيانات بالتواريخ والقيم المقابلة.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## الخطوة 4: احفظ المستند

 وأخيرًا، احفظ المستند في الدليل المحدد باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

يكمل هذا تنفيذ إدراج مخطط مساحي باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإدراج مخطط مساحي باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إدراج مخطط مساحي في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك إنشاء مستند جديد وإدراج مخطط مساحي وإضافة بيانات متسلسلة وحفظ المستند مع المخطط.

يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام المخططات في مستندات Word. باستخدام بضعة أسطر فقط من التعليمات البرمجية، يمكنك إنشاء مخططات مساحية ذات مظهر احترافي وتخصيصها وفقًا لمتطلباتك. تُستخدم المخططات المساحية بشكل شائع لعرض حجم البيانات واتجاهاتها بمرور الوقت أو الفئات.

باستخدام Aspose.Words for .NET، يمكنك أتمتة عملية إنشاء المستندات باستخدام المخططات المساحية، مما يوفر الوقت والجهد في إنشاء المستندات يدويًا. توفر المكتبة نطاقًا واسعًا من أنواع المخططات وخيارات التخصيص، مما يسمح لك بإنشاء مخططات جذابة وغنية بالمعلومات في مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س1. ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء مستندات Word وتعديلها وتحويلها برمجيًا في تطبيقات .NET. فهو يوفر مجموعة شاملة من واجهات برمجة التطبيقات لمعالجة الكلمات مع عناصر المستند، بما في ذلك المخططات والفقرات والجداول والمزيد.

#### س2. كيف أقوم بتثبيت Aspose.Words لـ .NET؟
لتثبيت Aspose.Words لـ .NET، يمكنك استخدام مدير الحزم NuGet في Visual Studio لتثبيت المكتبة مباشرة في مشروعك. ما عليك سوى البحث عن "Apose.Words" في مدير حزم NuGet وتثبيت الحزمة.

#### س3. هل يمكنني تخصيص مظهر المخطط المساحي؟
نعم، باستخدام Aspose.Words for .NET، يمكنك تخصيص جوانب مختلفة من مظهر المخطط المساحي. يمكنك تعديل خصائص مثل عنوان المخطط ولون السلسلة وتسميات المحاور وتنسيق منطقة المخطط. توفر المكتبة مجموعة غنية من واجهات برمجة التطبيقات للتحكم في العناصر المرئية للمخطط وإنشاء مظهر مخصص يناسب احتياجاتك.

#### س 4. هل يمكنني إضافة سلاسل متعددة إلى المخطط المساحي؟
نعم، يمكنك إضافة سلاسل متعددة إلى المخطط المساحي باستخدام Aspose.Words لـ .NET. تمثل كل سلسلة مجموعة من نقاط البيانات المرسومة على المخطط. يمكنك إضافة سلسلة بمجموعات بيانات مختلفة وتخصيص كل سلسلة على حدة، بما في ذلك اسمها ونقاط البيانات والمظهر.

#### س5. هل يمكنني حفظ المستند مع المخطط المساحي المدرج بتنسيقات مختلفة؟
 نعم، يسمح لك Aspose.Words for .NET بحفظ المستند باستخدام المخطط المساحي المدرج بتنسيقات مختلفة، مثل DOCX وPDF وHTML والمزيد. يمكنك اختيار تنسيق الإخراج المطلوب بناءً على متطلباتك واستخدام`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بالمخطط المساحي المدرج في المستند المحفوظ.

#### س6. هل يمكنني تعديل بيانات ومظهر المخطط المساحي بعد إدراجه؟
نعم، بعد إدراج المخطط المساحي في المستند، يمكنك تعديل بياناته ومظهره باستخدام واجهات برمجة التطبيقات التي يوفرها Aspose.Words لـ .NET. يمكنك تحديث بيانات السلسلة وتغيير نوع المخطط وتخصيص خصائص المحور وتطبيق خيارات التنسيق لإنشاء مخططات ديناميكية وتفاعلية في مستندات Word.