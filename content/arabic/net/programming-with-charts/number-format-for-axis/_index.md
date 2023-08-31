---
title: تنسيق الأرقام للمحور في مخطط
linktitle: تنسيق الأرقام للمحور في مخطط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعيين تنسيق الأرقام لمحور في مخطط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/number-format-for-axis/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين تنسيق الأرقام لمحور في الرسم البياني. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات سلسلة وتنسيق تسميات المحور.

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

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط عمودي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف خمسة عناصر بقيمها المقابلة.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## الخطوة 4: قم بتنسيق تسميات المحور

 لتعيين تنسيق الأرقام لتسميات المحور ص ، قم بالوصول إلى ملف`AxisY` خاصية الرسم البياني وتعيين`NumberFormat.FormatCode` إلى التنسيق المطلوب. في هذا المثال ، قمنا بتعيين التنسيق على "#، ## 0" لعرض الأرقام مع الآلاف من الفواصل.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## الخطوة 5: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

هذا يكمل تنفيذ إعداد تنسيق الأرقام للمحور باستخدام Aspose.Words for .NET.

### مثال على الكود المصدري لـ Number Format For Axis باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تعيين تنسيق الأرقام لمحور في مخطط باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد وإدراج مخطط عمودي وإضافة بيانات سلسلة وتنسيق تسميات المحور لعرض الأرقام بتنسيق معين.

يوفر Aspose.Words for .NET ميزات قوية لتخصيص مظهر المخططات في مستندات Word. من خلال تعيين تنسيق الأرقام لتسميات المحور ، يمكنك التحكم في كيفية عرض الأرقام ، بما في ذلك الخيارات مثل المنازل العشرية وفواصل الآلاف ورموز العملات والمزيد. يتيح لك ذلك تقديم البيانات الرقمية بطريقة واضحة وذات مغزى.

باستخدام Aspose.Words for .NET ، لديك المرونة في تنسيق جوانب مختلفة من المخطط ، بما في ذلك تسميات المحور. من خلال تعيين تنسيق الأرقام للمحور ، يمكنك ضمان التناسق وتحسين قابلية قراءة المخطط ، مما يسهل على المستخدمين تفسير القيم الممثلة.

### أسئلة وأجوبة

#### س 1. ما هو تنسيق الأرقام للمحور في الرسم البياني؟
يشير تنسيق الأرقام للمحور في المخطط إلى التنسيق المطبق على القيم الرقمية المعروضة على المحور. يتيح لك التحكم في كيفية عرض الأرقام ، بما في ذلك خيارات مثل المنازل العشرية وفواصل الآلاف ورموز العملات وعلامات النسبة المئوية والمزيد. من خلال تعيين تنسيق الأرقام ، يمكنك تخصيص مظهر البيانات الرقمية في المخطط لتناسب متطلباتك المحددة.

#### س 2. كيف يمكنني تعيين تنسيق الأرقام لتسميات المحور؟
 لتعيين تنسيق الأرقام لتسميات المحور في مخطط باستخدام Aspose.Words for .NET ، يمكنك الوصول إلى ملف`AxisY` خاصية الرسم البياني وتعيين`NumberFormat.FormatCode`الخاصية إلى رمز التنسيق المطلوب. يتبع رمز التنسيق بناء جملة أنماط التنسيق الرقمية القياسية ويحدد كيفية عرض الأرقام. على سبيل المثال ، يمكنك استخدام "#، ## 0.00" لعرض الأرقام مع منزلتين عشريتين وفواصل الآلاف.

#### س 3. هل يمكنني تعيين تنسيقات أرقام مختلفة لتسميات المحور س والمحور ص؟
نعم ، يمكنك تعيين تنسيقات أرقام مختلفة لتسميات المحور X والمحور Y باستخدام Aspose.Words for .NET. الوصول إلى المحور المعني (`AxisX` لمحور X أو`AxisY` للمحور ص) من المخطط وتعديل`NumberFormat.FormatCode` على حدة لكل محور. يتيح لك ذلك تطبيق تنسيقات أرقام مختلفة على التسميات الموجودة على كل محور بناءً على متطلباتك المحددة.

#### س 4. ما هي بعض رموز تنسيقات الأرقام الشائعة التي يمكنني استخدامها؟
يدعم Aspose.Words for .NET نطاقًا واسعًا من أكواد تنسيق الأرقام التي يمكنك استخدامها لتنسيق تسميات المحور في مخطط. تتضمن بعض رموز التنسيق الشائعة ما يلي:

- `0` أو`#` - يعرض الرقم بدون منازل عشرية.
- `0.00` أو`#.00` - يعرض الرقم مع منزلتين عشريتين.
- `#,##0` يعرض الرقم بآلاف الفواصل.
- `"€"0.00` - يعرض الرقم برمز عملة اليورو ومنزلتين عشريتين.
- `"%"0` - يعرض الرقم كنسبة مئوية.

 يمكنك العثور على مزيد من المعلومات حول الرقم[رموز التنسيق](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) في مرجع API لـ Aspose.Words لـ .NET.

#### س 5. هل يمكنني تخصيص الخصائص الأخرى لتسميات المحور؟
نعم ، يوفر Aspose.Words for .NET مجموعة واسعة من الخصائص لتخصيص مظهر وسلوك تسميات المحاور. بالإضافة إلى تنسيق الأرقام ، يمكنك تعديل خصائص مثل الخط والحجم واللون والاتجاه والمحاذاة والمزيد. يتيح لك ذلك تخصيص تسميات المحاور بالكامل لتلائم النمط المطلوب ومتطلبات العرض التقديمي.