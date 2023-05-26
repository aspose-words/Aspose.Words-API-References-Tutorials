---
title: ضع علامة على محاذاة تسمية متعددة الأسطر
linktitle: ضع علامة على محاذاة تسمية متعددة الأسطر
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية محاذاة تسميات التجزئة متعددة الأسطر في محور الرسم البياني باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-charts/tick-multi-line-label-alignment/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لتعيين محاذاة تسميات التجزئة متعددة الأسطر في محور المخطط. يوضح كود المصدر المقدم كيفية إنشاء مخطط والوصول إلى المحور وتعديل محاذاة تسمية التجزئة.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستند الناتج.

## الخطوة 2: أنشئ مستندًا جديدًا وأدخل مخططًا

 إنشاء ملف`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط مبعثر في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## الخطوة 3: ضبط محاذاة تسمية التجزئة

 لتعيين محاذاة تسميات التجزئة متعددة الأسطر ، قم بالوصول إلى`AxisX` خاصية الرسم البياني وتعيين`TickLabelAlignment` الخاصية للمحاذاة المطلوبة. في هذا المثال ، قمنا بتعيين المحاذاة إلى`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

هذا يكمل تنفيذ إعداد محاذاة تسمية العلامات متعددة الأسطر باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Tick Multi Line Label Alignment باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// هذه الخاصية لها تأثير فقط للتسميات متعددة الخطوط.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```