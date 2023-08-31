---
title: تحقق من تأثير النص DrawML
linktitle: تحقق من تأثير النص DrawML
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية التحقق من تأثيرات النص DrawML في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/check-drawingml-text-effect/
---

في هذا البرنامج التعليمي، سنرشدك إلى كيفية التحقق من تأثيرات النص DrawML في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يتيح لك التحقق من تأثيرات النص DrawML تحديد ما إذا تم تطبيق تأثير معين على جزء من النص. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك
- مستند Word يحتوي على تأثيرات نصية DrawML

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتحقق من تأثيرات النص
بعد ذلك، سنقوم بتحميل مستند Word والوصول إلى مجموعة عمليات التشغيل (تسلسلات الأحرف) في الفقرة الأولى من نص المستند. بعد ذلك، سوف نتحقق مما إذا تم تطبيق أي تأثيرات نصية محددة لـ DrawML على خط التشغيل الأول.

```csharp
// قم بتحميل المستند
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// تحقق من تأثيرات النص DrawML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### نموذج التعليمات البرمجية المصدر للتحقق من تأثير DMLText باستخدام Aspose.Words لـ .NET 

```csharp

//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// قد يتم تطبيق العديد من تأثيرات نص Dml في عملية تشغيل واحدة.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## خاتمة
في هذا البرنامج التعليمي، رأينا كيفية التحقق من تأثيرات النص DrawML في مستند Word باستخدام Aspose.Words لـ .NET. يتيح لك التحقق من تأثيرات النص DrawML تحديد أجزاء النص التي تم تطبيق تأثيرات معينة عليها. لا تتردد في استخدام هذه الميزة لمعالجة وتحليل تأثيرات النص في مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س: كيف يمكنني الوصول إلى تأثيرات النص DrawML في مستند Word باستخدام Aspose.Words؟

ج: باستخدام Aspose.Words، يمكنك الوصول إلى تأثيرات نص DrawML في مستند Word باستخدام واجهة برمجة التطبيقات المتوفرة. يمكنك تصفح عناصر النص والتحقق من خصائص معينة لتأثيرات النص، مثل اللون والحجم وما إلى ذلك.

#### س: ما هي أنواع تأثيرات النص DrawML المستخدمة بشكل شائع في مستندات Word؟

ج: تتضمن أنواع تأثيرات النص DrawML شائعة الاستخدام في مستندات Word الظلال والانعكاسات والتوهجات والتدرجات وما إلى ذلك. ويمكن تطبيق هذه التأثيرات لتحسين مظهر النص وتنسيقه.

#### س: كيف يمكنني التحقق من لون تأثير النص DrawML في مستند Word؟

ج: للتحقق من لون تأثير النص DrawML في مستند Word، يمكنك استخدام الطرق التي يوفرها Aspose.Words للوصول إلى خصائص اللون لتأثير النص. بهذه الطريقة يمكنك الحصول على اللون المستخدم لتأثير النص المحدد.

#### س: هل يمكن التحقق من تأثيرات النص في مستندات Word التي تحتوي على أقسام متعددة؟

ج: نعم، يسمح Aspose.Words بفحص تأثيرات النص في مستندات Word التي تحتوي على أقسام متعددة. يمكنك التنقل عبر كل قسم من المستند والوصول إلى تأثيرات النص لكل قسم على حدة.

#### س: كيف يمكنني التحقق من عتامة تأثير النص DrawML في مستند Word؟

ج: للتحقق من عتامة تأثير النص DrawML في مستند Word، يمكنك استخدام الطرق التي يوفرها Aspose.Words للوصول إلى خصائص العتامة لتأثير النص. سيسمح لك هذا بتطبيق قيمة العتامة على تأثير النص المحدد.