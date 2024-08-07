---
title: وحدة القياس
linktitle: وحدة القياس
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تكوين ميزة وحدة القياس في Aspose.Words لـ .NET للحفاظ على تنسيق المستند أثناء تحويل ODT.
type: docs
weight: 10
url: /ar/net/programming-with-odtsaveoptions/measure-unit/
---
## مقدمة

هل اضطررت من قبل إلى تحويل مستندات Word الخاصة بك إلى تنسيقات مختلفة ولكنك بحاجة إلى وحدة قياس محددة لتخطيطك؟ سواء كنت تتعامل مع البوصات أو السنتيمترات أو النقاط، فإن التأكد من احتفاظ المستند بسلامته أثناء عملية التحويل أمر بالغ الأهمية. في هذا البرنامج التعليمي، سنتعرف على كيفية تكوين ميزة وحدة القياس في Aspose.Words لـ .NET. تضمن هذه الميزة القوية الحفاظ على تنسيق المستند الخاص بك تمامًا كما تحتاج إليه عند التحويل إلى تنسيق ODT (نص المستند المفتوح).

## المتطلبات الأساسية

قبل الغوص في التعليمات البرمجية، هناك بعض الأشياء التي ستحتاج إليها للبدء:

1. Aspose.Words for .NET: تأكد من تثبيت أحدث إصدار من Aspose.Words for .NET. إذا لم يكن لديك بعد، يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: بيئة تطوير متكاملة (IDE) مثل Visual Studio لكتابة كود C# وتنفيذه.
3. المعرفة الأساسية بـ C#: إن فهم أساسيات C# سيساعدك على متابعة البرنامج التعليمي.
4. مستند Word: احصل على نموذج مستند Word جاهزًا يمكنك استخدامه للتحويل.

## استيراد مساحات الأسماء

قبل أن نبدأ بالبرمجة، دعونا نتأكد من أننا قمنا باستيراد مساحات الأسماء الضرورية. قم بإضافة هذه التعليمات باستخدام التوجيهات الموجودة أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

أولاً، تحتاج إلى تحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الخاص بك والمكان الذي سيتم فيه حفظ الملف المحول.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى الدليل الخاص بك. وهذا يضمن أن التعليمات البرمجية الخاصة بك تعرف مكان العثور على مستند Word الخاص بك.

## الخطوة 2: قم بتحميل مستند Word

 بعد ذلك، تحتاج إلى تحميل مستند Word الذي تريد تحويله. ويتم ذلك باستخدام`Document` فئة من Aspose.Words.

```csharp
// قم بتحميل مستند الوورد
Document doc = new Document(dataDir + "Document.docx");
```

تأكد من وجود مستند Word المسمى "Document.docx" في الدليل المحدد.

## الخطوة 3: تكوين وحدة القياس

 الآن، لنقم بتكوين وحدة القياس لتحويل ODT. هذا هو المكان الذي يحدث فيه السحر. سنقوم بإعداد`OdtSaveOptions` لاستخدام البوصة كوحدة القياس.

```csharp
// تكوين خيارات النسخ الاحتياطي مع ميزة "وحدة القياس".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 في هذا المثال، نقوم بتعيين وحدة القياس إلى بوصة. يمكنك أيضًا اختيار وحدات أخرى مثل`OdtSaveMeasureUnit.Centimeters` أو`OdtSaveMeasureUnit.Points` اعتمادا على الاحتياجات الخاصة بك.

## الخطوة 4: تحويل المستند إلى ODT

 وأخيرًا، سنقوم بتحويل مستند Word إلى تنسيق ODT باستخدام الملف الذي تم تكوينه`OdtSaveOptions`.

```csharp
// تحويل المستند إلى ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

يحفظ سطر التعليمات البرمجية هذا المستند المحول في الدليل المحدد مع تطبيق وحدة القياس الجديدة.

## خاتمة

وهنا لديك! باتباع هذه الخطوات، يمكنك بسهولة تكوين ميزة وحدة القياس في Aspose.Words لـ .NET لضمان الحفاظ على تخطيط المستند أثناء التحويل. سواء كنت تستخدم البوصات أو السنتيمترات أو النقاط، فقد أوضح لك هذا البرنامج التعليمي كيفية التحكم في تنسيق المستند بسهولة.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية للعمل مع مستندات Word برمجيًا. فهو يسمح للمطورين بإنشاء مستندات Word وتعديلها وتحويلها ومعالجتها دون الحاجة إلى Microsoft Word.

### هل يمكنني استخدام وحدات قياس أخرى غير البوصة؟
 نعم، يدعم Aspose.Words for .NET وحدات القياس الأخرى مثل السنتيمترات والنقاط. يمكنك تحديد الوحدة المطلوبة باستخدام`OdtSaveMeasureUnit` تعداد.

### هل تتوفر نسخة تجريبية مجانية من Aspose.Words لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Words لـ .NET من[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق Aspose.Words لـ .NET؟
 يمكنك الوصول إلى الوثائق الشاملة لـ Aspose.Words for .NET على[هذا الرابط](https://reference.aspose.com/words/net/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟
 للحصول على الدعم، يمكنك زيارة منتدى Aspose.Words على[هذا الرابط](https://forum.aspose.com/c/words/8).
