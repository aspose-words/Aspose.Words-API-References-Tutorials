---
title: تعيين موضع الحاشية السفلية وموضع الملاحظة النهائية
linktitle: تعيين موضع الحاشية السفلية وموضع الملاحظة النهائية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مواضع الحواشي السفلية والتعليقات الختامية في مستندات Word باستخدام Aspose.Words لـ .NET مع هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## مقدمة

إذا كنت تعمل مع مستندات Word وتحتاج إلى إدارة الحواشي السفلية والتعليقات الختامية بفعالية، فإن Aspose.Words for .NET هي مكتبتك المفضلة. سيرشدك هذا البرنامج التعليمي إلى كيفية تعيين مواضع الحواشي السفلية والتعليقات الختامية في مستند Word باستخدام Aspose.Words for .NET. سنقوم بتفصيل كل خطوة لتسهيل متابعتها وتنفيذها.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:

-  Aspose.Words لمكتبة .NET: يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
- Visual Studio: أي إصدار حديث سيعمل بشكل جيد.
- المعرفة الأساسية بـ C#: سيساعدك فهم الأساسيات على المتابعة بسهولة.

## استيراد مساحات الأسماء

أولاً، قم باستيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using System;
using Aspose.Words;
```

## الخطوة 1: قم بتحميل مستند Word

للبدء، تحتاج إلى تحميل مستند Word الخاص بك في كائن مستند Aspose.Words. سيسمح لك ذلك بمعالجة محتويات المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 في هذا الكود استبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي حيث يوجد المستند الخاص بك.

## الخطوة 2: تعيين موضع الحاشية السفلية

بعد ذلك، ستقوم بتعيين موضع الحواشي السفلية. يسمح لك Aspose.Words for .NET بوضع الحواشي السفلية إما في أسفل الصفحة أو أسفل النص.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 هنا، قمنا بتعيين الحواشي السفلية لتظهر أسفل النص. إذا كنت تفضلها في أسفل الصفحة، فاستخدمها`FootnotePosition.BottomOfPage`.

## الخطوة 3: تعيين موضع التعليق الختامي

وبالمثل، يمكنك تعيين موضع التعليقات الختامية. يمكن وضع التعليقات الختامية إما في نهاية القسم أو في نهاية المستند.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 في هذا المثال، يتم وضع التعليقات الختامية في نهاية كل قسم. لوضعها في نهاية المستند، استخدم`EndnotePosition.EndOfDocument`.

## الخطوة 4: احفظ المستند

وأخيرا، احفظ المستند لتطبيق التغييرات. تأكد من تحديد مسار الملف الصحيح واسم مستند الإخراج.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

يحفظ هذا السطر المستند المعدل في الدليل المحدد.

## خاتمة

يعد تعيين مواضع الحواشي السفلية والتعليقات الختامية في مستندات Word باستخدام Aspose.Words لـ .NET أمرًا سهلاً بمجرد معرفة الخطوات. باتباع هذا الدليل، يمكنك تخصيص مستنداتك لتناسب احتياجاتك، مما يضمن وضع الحواشي السفلية والتعليقات الختامية في المكان الذي تريده بالضبط.

## الأسئلة الشائعة

### هل يمكنني تعيين مواضع مختلفة للحواشي السفلية أو التعليقات الختامية الفردية؟

لا، يقوم Aspose.Words for .NET بتعيين موضع كافة الحواشي السفلية والتعليقات الختامية في المستند بشكل موحد.

### هل يتوافق Aspose.Words for .NET مع كافة إصدارات مستندات Word؟

نعم، يدعم Aspose.Words for .NET نطاقًا واسعًا من تنسيقات مستندات Word، بما في ذلك DOC وDOCX وRTF والمزيد.

### هل يمكنني استخدام Aspose.Words لـ .NET مع لغات البرمجة الأخرى؟

تم تصميم Aspose.Words for .NET لتطبيقات .NET، ولكن يمكنك استخدامه مع أي لغة تدعم .NET مثل C#، وVB.NET، وما إلى ذلك.

### هل تتوفر نسخة تجريبية مجانية من Aspose.Words لـ .NET؟

 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق أكثر تفصيلاً حول Aspose.Words for .NET؟

 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/words/net/).