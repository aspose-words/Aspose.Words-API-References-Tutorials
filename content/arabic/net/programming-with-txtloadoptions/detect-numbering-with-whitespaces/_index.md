---
title: كشف الترقيم مع المسافات البيضاء
linktitle: كشف الترقيم مع المسافات البيضاء
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: اكتشف كيفية استخدام Aspose.Words for .NET لاكتشاف الترقيم باستخدام المسافات البيضاء في المستندات ذات النص العادي والتأكد من التعرف على قوائمك بشكل صحيح.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## مقدمة

Aspose.Words لعشاق .NET! اليوم، نحن نتعمق في ميزة رائعة يمكن أن تجعل قوائم التعامل مع المستندات النصية العادية أمرًا سهلاً. هل سبق لك أن تعاملت مع ملفات نصية حيث من المفترض أن تكون بعض الأسطر عبارة عن قوائم، لكنها لا تبدو صحيحة تمامًا عند تحميلها في مستند Word؟ حسنًا، لدينا خدعة رائعة في جعبتنا: اكتشاف الترقيم باستخدام المسافات البيضاء. سيرشدك هذا البرنامج التعليمي إلى كيفية استخدام`DetectNumberingWithWhitespaces` في Aspose.Words for .NET لضمان التعرف على قوائمك بشكل صحيح، حتى في حالة وجود مسافة بيضاء بين الأرقام والنص.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

-  Aspose.Words for .NET: يمكنك تنزيله من[إصدارات Aspose](https://releases.aspose.com/words/net/) صفحة.
- بيئة التطوير: Visual Studio أو أي C# IDE آخر.
- .NET Framework مثبتًا على جهازك.
- المعرفة الأساسية بـ C#: سيساعدك فهم الأساسيات على متابعة الأمثلة.

## استيراد مساحات الأسماء

قبل الانتقال إلى التعليمات البرمجية، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك. إليك مقتطف سريع للبدء:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

دعونا نقسم العملية إلى خطوات بسيطة يمكن التحكم فيها. سترشدك كل خطوة إلى التعليمات البرمجية الضرورية وتشرح لك ما يحدث.

## الخطوة 1: تحديد دليل المستندات الخاص بك

أول الأشياء أولاً، لنقم بإعداد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي سيتم فيه تخزين ملفات الإدخال والإخراج.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند نص عادي

بعد ذلك، سنقوم بإنشاء مستند نص عادي كسلسلة. ستحتوي هذه الوثيقة على أجزاء يمكن تفسيرها على أنها قوائم.

```csharp
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";
```

## الخطوة 3: تكوين خيارات التحميل

 للكشف عن الترقيم بمسافات بيضاء، نحتاج إلى تعيين`DetectNumberingWithWhitespaces` خيار ل`true` في`TxtLoadOptions` هدف.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## الخطوة 4: قم بتحميل المستند

 الآن، لنقم بتحميل المستند باستخدام ملف`TxtLoadOptions` كمعلمة. وهذا يضمن اكتشاف القائمة الرابعة (التي تحتوي على مسافات بيضاء) بشكل صحيح.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## الخطوة 5: احفظ المستند

وأخيرًا، احفظ المستند في الدليل المحدد. سيؤدي هذا إلى إخراج مستند Word يحتوي على قوائم تم اكتشافها بشكل صحيح.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## خاتمة

وهناك لديك! باستخدام بضعة أسطر فقط من التعليمات البرمجية، تكون قد أتقنت فن اكتشاف الترقيم باستخدام المسافات البيضاء في المستندات ذات النص العادي باستخدام Aspose.Words for .NET. يمكن أن تكون هذه الميزة مفيدة بشكل لا يصدق عند التعامل مع تنسيقات نصية مختلفة والتأكد من تمثيل قوائمك بدقة في مستندات Word الخاصة بك. لذلك، في المرة القادمة التي تواجه فيها تلك القوائم الصعبة، ستعرف بالضبط ما يجب عليك فعله.

## الأسئلة الشائعة

###  ما هو`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` هو خيار في`TxtLoadOptions` يسمح لـ Aspose.Words بالتعرف على القوائم حتى في حالة وجود مسافة بيضاء بين الترقيم ونص عنصر القائمة.

### هل يمكنني استخدام هذه الميزة لمحددات أخرى مثل التعداد النقطي والأقواس؟
 نعم، يقوم Aspose.Words تلقائيًا باكتشاف القوائم ذات المحددات الشائعة مثل التعداد النقطي والأقواس. ال`DetectNumberingWithWhitespaces` يساعد بشكل خاص في القوائم التي تحتوي على مسافات بيضاء.

###  ماذا يحدث إذا لم أستخدم`DetectNumberingWithWhitespaces`?
بدون هذا الخيار، قد لا يتم التعرف على القوائم التي تحتوي على مسافات بيضاء بين الترقيم والنص كقوائم، ويمكن أن تظهر العناصر كفقرات عادية.

### هل هذه الميزة متوفرة في منتجات Aspose الأخرى؟
تم تصميم هذه الميزة المحددة خصيصًا لـ Aspose.Words for .NET، والمصممة للتعامل مع معالجة مستندات Word.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت من[Aspose الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) صفحة.

