---
title: إدراج مخطط مبعثر في مستند Word
linktitle: إدراج مخطط مبعثر في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج مخطط مبعثر في Word باستخدام Aspose.Words لـ .NET. خطوات سهلة لدمج تمثيلات البيانات المرئية في مستنداتك.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-scatter-chart/
---
## مقدمة

ستتعلم في هذا البرنامج التعليمي كيفية الاستفادة من Aspose.Words لـ .NET لإدراج مخطط مبعثر في مستند Word الخاص بك. تعد المخططات المبعثرة أدوات مرئية قوية يمكنها عرض نقاط البيانات بشكل فعال بناءً على متغيرين، مما يجعل مستنداتك أكثر جاذبية وغنية بالمعلومات.

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء مخططات مبعثرة باستخدام Aspose.Words لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

1.  تثبيت Aspose.Words لـ .NET: قم بتنزيل Aspose.Words لـ .NET وتثبيته من[هنا](https://releases.aspose.com/words/net/).
   
2. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# وإطار عمل .NET سيكون مفيدًا.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

الآن، دعنا نقسم عملية إدراج مخطط مبعثر في مستند Word الخاص بك باستخدام Aspose.Words for .NET:

## الخطوة 1: تهيئة المستند وDocumentBuilder

 أولاً، قم بتهيئة مثيل جديد لـ`Document` الطبقة و`DocumentBuilder` class لبدء إنشاء المستند الخاص بك.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل المخطط المبعثر

 استخدم ال`InsertChart` طريقة`DocumentBuilder` فئة لإدراج مخطط مبعثر في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: إضافة سلسلة البيانات إلى المخطط

الآن، قم بإضافة سلسلة البيانات إلى المخطط المبعثر الخاص بك. يوضح هذا المثال إضافة سلسلة بنقاط بيانات محددة.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## الخطوة 4: احفظ المستند

 وأخيرًا، احفظ المستند المعدل في الموقع الذي تريده باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إدراج مخطط مبعثر في مستند Word الخاص بك باستخدام Aspose.Words for .NET. تعد المخططات المبعثرة أدوات ممتازة لتصور علاقات البيانات، وباستخدام Aspose.Words، يمكنك دمجها بسهولة في مستنداتك لتحسين الوضوح والفهم.

## الأسئلة الشائعة

### هل يمكنني تخصيص مظهر المخطط المبعثر باستخدام Aspose.Words؟
نعم، يسمح Aspose.Words بالتخصيص الشامل لخصائص المخطط مثل الألوان والمحاور والتسميات.

### هل Aspose.Words متوافق مع الإصدارات المختلفة من Microsoft Word؟
يدعم Aspose.Words إصدارات مختلفة من Microsoft Word، مما يضمن التوافق عبر الأنظمة الأساسية.

### هل يوفر Aspose.Words الدعم لأنواع أخرى من المخططات؟
نعم، يدعم Aspose.Words مجموعة واسعة من أنواع المخططات بما في ذلك المخططات الشريطية، والمخططات الخطية، والمخططات الدائرية.

### هل يمكنني تحديث البيانات ديناميكيًا في المخطط المبعثر برمجيًا؟
بالتأكيد، يمكنك تحديث بيانات المخطط ديناميكيًا باستخدام استدعاءات Aspose.Words API.

### أين يمكنني الحصول على مزيد من المساعدة أو الدعم لـ Aspose.Words؟
 لمزيد من المساعدة، قم بزيارة[منتدى دعم Aspose.Words](https://forum.aspose.com/c/words/8).