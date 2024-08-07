---
title: إلغاء ربط الرؤوس والتذييلات
linktitle: إلغاء ربط الرؤوس والتذييلات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلغاء ربط الرؤوس والتذييلات في مستندات Word باستخدام Aspose.Words لـ .NET. اتبع دليلنا التفصيلي خطوة بخطوة لإتقان التعامل مع المستندات.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/unlink-headers-footers/
---
## مقدمة

في عالم معالجة المستندات، قد يمثل الحفاظ على تناسق الرؤوس والتذييلات تحديًا في بعض الأحيان. سواء كنت تقوم بدمج المستندات أو تبحث فقط عن رؤوس وتذييلات مختلفة لأقسام مختلفة، فإن معرفة كيفية إلغاء ربطها أمر ضروري. اليوم، سوف نتعمق في كيفية تحقيق ذلك باستخدام Aspose.Words for .NET. سنقوم بتقسيمها خطوة بخطوة حتى تتمكن من المتابعة بسهولة. هل أنت مستعد لإتقان التعامل مع المستندات؟ دعونا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل الجوهرية، هناك بعض الأشياء التي ستحتاج إليها:

-  Aspose.Words لمكتبة .NET: يمكنك تنزيله من[صفحة الإصدارات Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: تأكد من تثبيت إطار عمل .NET متوافق.
- IDE: Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة مع .NET.
- الفهم الأساسي لـ C#: ستحتاج إلى فهم أساسي للغة البرمجة C#.

## استيراد مساحات الأسماء

للبدء، تأكد من استيراد مساحات الأسماء الضرورية في مشروعك. سيمكنك هذا من الوصول إلى مكتبة Aspose.Words وميزاتها.

```csharp
using Aspose.Words;
```

دعنا نقسم العملية إلى خطوات يمكن التحكم فيها لمساعدتك على إلغاء ربط الرؤوس والتذييلات في مستندات Word الخاصة بك.

## الخطوة 1: قم بإعداد مشروعك

أولاً، ستحتاج إلى إعداد بيئة مشروعك. افتح IDE الخاص بك وقم بإنشاء مشروع .NET جديد. أضف مرجعًا إلى مكتبة Aspose.Words التي قمت بتنزيلها مسبقًا.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند المصدر

بعد ذلك، تحتاج إلى تحميل المستند المصدر الذي تريد تعديله. سيتم إلغاء ربط الرؤوس والتذييلات الخاصة بهذا المستند.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## الخطوة 3: قم بتحميل مستند الوجهة

الآن، قم بتحميل المستند الوجهة حيث ستقوم بإلحاق المستند المصدر بعد إلغاء ربط الرؤوس والتذييلات الخاصة به.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 4: قم بإلغاء ربط الرؤوس والتذييلات

 هذه الخطوة حاسمة. لإلغاء ربط رؤوس وتذييلات المستند المصدر بتلك الموجودة في المستند الوجهة، ستستخدم الخيار`LinkToPrevious` طريقة. تضمن هذه الطريقة عدم انتقال الرؤوس والتذييلات إلى المستند الملحق.

```csharp
// قم بإلغاء ربط الرؤوس والتذييلات في المستند المصدر لإيقاف ذلك
//من متابعة رؤوس وتذييلات المستند الوجهة.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## الخطوة 5: إلحاق المستند المصدر

 بعد إلغاء ربط الرؤوس والتذييلات، يمكنك إلحاق المستند المصدر بالمستند الوجهة. استخدم`AppendDocument` الطريقة واضبط وضع تنسيق الاستيراد على`KeepSourceFormatting` للحفاظ على التنسيق الأصلي للمستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ الوثيقة النهائية

وأخيرًا، احفظ المستند الذي تم إنشاؤه حديثًا. سيتم إلحاق محتوى المستند المصدر بالمستند الوجهة في هذا المستند، مع إلغاء ربط الرؤوس والتذييلات.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## خاتمة

وهنا لديك! باتباع هذه الخطوات، تكون قد نجحت في إلغاء ربط الرؤوس والتذييلات في مستندك المصدر وإلحاقها بالمستند الوجهة باستخدام Aspose.Words for .NET. يمكن أن تكون هذه التقنية مفيدة بشكل خاص عند العمل مع مستندات معقدة تتطلب رؤوس وتذييلات مختلفة لأقسام مختلفة. ترميز سعيد!

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟  
Aspose.Words for .NET هي مكتبة قوية للعمل مع مستندات Word في تطبيقات .NET. يسمح للمطورين بإنشاء المستندات وتعديلها وتحويلها وطباعتها برمجيًا.

### هل يمكنني إلغاء ربط الرؤوس والتذييلات لأقسام محددة فقط؟  
 نعم، يمكنك إلغاء ربط الرؤوس والتذييلات لأقسام معينة عن طريق الوصول إلى`HeadersFooters` خاصية القسم المطلوب واستخدام`LinkToPrevious` طريقة.

### هل من الممكن الحفاظ على التنسيق الأصلي للوثيقة المصدر؟  
 نعم، عند إلحاق المستند المصدر، استخدم`ImportFormatMode.KeepSourceFormatting` خيار الاحتفاظ بالتنسيق الأصلي.

### هل يمكنني استخدام Aspose.Words لـ .NET مع لغات .NET الأخرى إلى جانب C#؟  
قطعاً! يمكن استخدام Aspose.Words لـ .NET مع أي لغة .NET، بما في ذلك VB.NET وF#.

### أين يمكنني العثور على مزيد من الوثائق والدعم لـ Aspose.Words لـ .NET؟  
 يمكنك العثور على وثائق شاملة عن[Aspose.Words لصفحة وثائق .NET](https://reference.aspose.com/words/net/) ، والدعم متاح على[منتدى Aspose](https://forum.aspose.com/c/words/8).
