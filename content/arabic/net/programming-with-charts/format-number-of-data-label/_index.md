---
title: تنسيق رقم تسمية البيانات في المخطط
linktitle: تنسيق رقم تسمية البيانات في المخطط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنسيق تسميات البيانات في المخططات باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة. قم بتحسين مستندات Word الخاصة بك دون عناء.
type: docs
weight: 10
url: /ar/net/programming-with-charts/format-number-of-data-label/
---
## مقدمة

غالبًا ما يتضمن إنشاء مستندات جذابة وغنية بالمعلومات تضمين مخططات تحتوي على تسميات بيانات منسقة جيدًا. إذا كنت أحد مطوري .NET وتتطلع إلى تحسين مستندات Word الخاصة بك باستخدام مخططات معقدة، فإن Aspose.Words for .NET هي مكتبة رائعة لمساعدتك في تحقيق ذلك. سيرشدك هذا البرنامج التعليمي خلال عملية تنسيق تسميات الأرقام في مخطط باستخدام Aspose.Words for .NET، خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في الكود، هناك بعض المتطلبات الأساسية التي يجب عليك توفرها:

-  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words for .NET. إذا لم تقم بتثبيته بعد، يمكنك ذلك[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: يجب أن يكون لديك بيئة تطوير .NET. يوصى بشدة باستخدام Visual Studio.
- المعرفة الأساسية بـ C#: يعد الإلمام ببرمجة C# أمرًا ضروريًا لأن هذا البرنامج التعليمي يتضمن كتابة وفهم كود C#.
-  الترخيص المؤقت: لاستخدام Aspose.Words دون أي قيود، يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/).

الآن، دعنا نتعمق في عملية تنسيق تسميات الأرقام في المخطط خطوة بخطوة.

## استيراد مساحات الأسماء

أول الأشياء أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Words لـ .NET. أضف الأسطر التالية في أعلى ملف C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

قبل أن تتمكن من البدء في التعامل مع مستند Word الخاص بك، تحتاج إلى تحديد الدليل الذي سيتم حفظ المستند فيه. يعد هذا ضروريًا لعملية الحفظ لاحقًا.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: تهيئة المستند و DocumentBuilder

 الخطوة التالية هي تهيئة ملف جديد`Document` و أ`DocumentBuilder` . ال`DocumentBuilder` هي فئة مساعدة تسمح لنا ببناء محتوى المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل مخططًا في المستند

 الآن، لنقم بإدراج مخطط في المستند باستخدام الأمر`DocumentBuilder`. في هذا البرنامج التعليمي، سنستخدم المخطط الخطي كمثال.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

هنا، نقوم بإدراج مخطط خطي بعرض وارتفاع محددين، ونقوم بتعيين عنوان المخطط.

## الخطوة 4: مسح السلسلة الافتراضية وإضافة سلسلة جديدة

افتراضيًا، سيحتوي المخطط على بعض السلاسل التي تم إنشاؤها مسبقًا. نحتاج إلى مسحها وإضافة سلسلتنا الخاصة بنقاط بيانات محددة.

```csharp
// حذف السلسلة التي تم إنشاؤها افتراضيًا.
chart.Series.Clear();

// أضف سلسلة جديدة بنقاط بيانات مخصصة.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## الخطوة 5: تمكين تسميات البيانات

لعرض تسميات البيانات على المخطط، نحتاج إلى تمكينها لسلسلتنا.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## الخطوة 6: تنسيق تسميات البيانات

جوهر هذا البرنامج التعليمي هو تنسيق تسميات البيانات. يمكننا تطبيق تنسيقات أرقام مختلفة على كل تسمية بيانات على حدة.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // تنسيق العملة
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // تنسيق التاريخ
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // تنسيق النسبة المئوية
```

 بالإضافة إلى ذلك، يمكنك ربط تنسيق تسمية البيانات بخلية مصدر. عند الارتباط،`NumberFormat` سيتم إعادة تعيينه إلى عام ويتم توريثه من الخلية المصدر.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## الخطوة 7: احفظ المستند

وأخيرا، احفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

يؤدي هذا إلى حفظ المستند الخاص بك بالاسم المحدد ويضمن الحفاظ على المخطط الخاص بك مع تسميات البيانات المنسقة.

## خاتمة

يمكن أن يؤدي تنسيق تسميات البيانات في مخطط باستخدام Aspose.Words for .NET إلى تحسين سهولة القراءة والكفاءة المهنية لمستندات Word الخاصة بك. باتباع هذا الدليل خطوة بخطوة، من المفترض أن تتمكن الآن من إنشاء مخطط وإضافة سلسلة بيانات وتنسيق تسميات البيانات لتلبية احتياجاتك. تعد Aspose.Words for .NET أداة قوية تسمح بالتخصيص الشامل والأتمتة لمستندات Word، مما يجعلها أصلًا لا يقدر بثمن لمطوري .NET.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word ومعالجتها وتحويلها برمجيًا باستخدام لغة C#.

### هل يمكنني تنسيق أنواع أخرى من المخططات باستخدام Aspose.Words لـ .NET؟
نعم، يدعم Aspose.Words for .NET مجموعة متنوعة من أنواع المخططات، بما في ذلك الشريط والعمود والدائري والمزيد.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### هل من الممكن ربط تسميات البيانات بالخلايا المصدر في Excel؟
نعم، يمكنك ربط تسميات البيانات بالخلايا المصدر، مما يسمح بتوارث تنسيق الأرقام من الخلية المصدر.

### أين يمكنني العثور على وثائق أكثر تفصيلاً حول Aspose.Words for .NET؟
 يمكنك العثور على وثائق شاملة[هنا](https://reference.aspose.com/words/net/).
