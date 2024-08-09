---
title: تخصيص تسمية بيانات المخطط
linktitle: تخصيص تسمية بيانات المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تخصيص تسميات بيانات المخطط باستخدام Aspose.Words for .NET في دليل خطوة بخطوة. مثالي لمطوري .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/chart-data-label/
---
## مقدمة

هل تتطلع إلى تحسين تطبيقات .NET الخاصة بك من خلال إمكانيات معالجة المستندات الديناميكية والمخصصة؟ Aspose.Words for .NET قد يكون مجرد إجابتك! في هذا الدليل، سنتعمق في تخصيص تسميات بيانات المخطط باستخدام Aspose.Words for .NET، وهي مكتبة قوية لإنشاء مستندات Word وتعديلها وتحويلها. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيرشدك هذا البرنامج التعليمي خلال كل خطوة، مما يضمن فهمك لكيفية استخدام هذه الأداة بفعالية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: قم بتثبيت Visual Studio 2019 أو إصدار أحدث.
2. .NET Framework: تأكد من أن لديك .NET Framework 4.0 أو إصدار أحدث.
3.  Aspose.Words لـ .NET: قم بتنزيل Aspose.Words لـ .NET وتثبيته من[رابط التحميل](https://releases.aspose.com/words/net/).
4. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# أمر ضروري.
5.  ترخيص صالح: احصل على أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) أو شراء واحدة من[رابط الشراء](https://purchase.aspose.com/buy).

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. تعتبر هذه الخطوة حاسمة لأنها تضمن لك الوصول إلى جميع الفئات والأساليب التي يوفرها Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## الخطوة 1: تهيئة المستند وDocumentBuilder

لإنشاء مستندات Word ومعالجتها، نحتاج أولاً إلى تهيئة مثيل لـ`Document` فئة و أ`DocumentBuilder` هدف.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### توضيح

- مستند المستند: يقوم بإنشاء مثيل جديد لفئة المستند.
- منشئ DocumentBuilder: يساعد DocumentBuilder في إدراج المحتوى في كائن المستند.

## الخطوة 2: أدخل مخططًا

 بعد ذلك، سنقوم بإدراج مخطط شريطي في المستند باستخدام الملف`DocumentBuilder` هدف.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### توضيح

- شكل الشكل: يمثل المخطط كشكل في المستند.
- builder.InsertChart(ChartType.Bar, 432, 252): إدراج مخطط شريطي بأبعاد محددة.

## الخطوة 3: الوصول إلى سلسلة المخططات

لتخصيص تسميات البيانات، نحتاج أولاً إلى الوصول إلى السلسلة في المخطط.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### توضيح

- ChartSeries series0: استرداد السلسلة الأولى من المخطط، والتي سنقوم بتخصيصها.

## الخطوة 4: تخصيص تسميات البيانات

يمكن تخصيص تسميات البيانات لعرض معلومات متنوعة. سنقوم بتكوين التسميات لإظهار مفتاح وسيلة الإيضاح واسم السلسلة والقيمة، مع إخفاء اسم الفئة والنسبة المئوية.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### توضيح

- تسميات ChartDataLabelCollection: الوصول إلى تسميات البيانات الخاصة بالسلسلة.
- labels.ShowLegendKey: يعرض مفتاح وسيلة الإيضاح.
- labels.ShowLeaderLines: إظهار الخطوط الرئيسية لتسميات البيانات الموضوعة بعيدًا عن نقاط البيانات.
- labels.ShowCategoryName: يخفي اسم الفئة.
- labels.ShowPercentage: إخفاء قيمة النسبة المئوية.
- labels.ShowSeriesName: يعرض اسم السلسلة.
- labels.ShowValue: يعرض قيمة نقاط البيانات.
- labels.Separator: يضبط الفاصل لتسميات البيانات.

## الخطوة 5: احفظ المستند

وأخيرا، احفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### توضيح

- doc.Save: يحفظ المستند بالاسم المحدد في الدليل المقدم.

## خاتمة

 تهانينا! لقد نجحت في تخصيص تسميات بيانات المخطط باستخدام Aspose.Words لـ .NET. توفر هذه المكتبة حلاً قويًا للتعامل مع مستندات Word برمجيًا، مما يسهل على المطورين إنشاء تطبيقات معالجة مستندات متطورة وديناميكية. الغوص في[الوثائق](https://reference.aspose.com/words/net/) لاستكشاف المزيد من الميزات والقدرات.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word وتعديلها وتحويلها برمجيًا.

### كيف أقوم بتثبيت Aspose.Words لـ .NET؟
 يمكنك تنزيله وتثبيته من[رابط التحميل](https://releases.aspose.com/words/net/). اتبع تعليمات التثبيت المقدمة.

### هل يمكنني تجربة Aspose.Words لـ .NET مجانًا؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) أو أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)لتقييم المنتج.

### هل Aspose.Words for .NET متوافق مع .NET Core؟
نعم، Aspose.Words for .NET متوافق مع .NET Core، و.NET Standard، و.NET Framework.

### أين يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟
 يمكنك زيارة[منتدى الدعم](https://forum.aspose.com/c/words/8) للحصول على المساعدة والمساعدة من مجتمع Aspose والخبراء.
