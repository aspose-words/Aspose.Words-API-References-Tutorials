---
title: فتح ميزات النوع
linktitle: فتح ميزات النوع
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words لـ .NET
type: docs
weight: 10
url: /ar/net/enable-opentype-features/open-type-features/
---

في هذا البرنامج التعليمي الشامل، ستتعلم كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستكون قادرًا على العمل باستخدام ميزات Open Type في مستندات Word الخاصة بك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: قم بتحميل المستند
للبدء، قم بتحميل المستند باستخدام فئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## الخطوة 2: تمكين ميزات النوع المفتوح
لتمكين ميزات Open Type، قم بتعيين خاصية TextShaperFactory الخاصة بفئة LayoutOptions إلى مثيل مصنع تشكيل النص المطلوب. في هذا المثال، نستخدم HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## الخطوة 3: احفظ المستند
بعد تمكين ميزات Open Type، احفظ المستند بتنسيق الإخراج المطلوب، مثل PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### مثال على كود المصدر لميزات الكتابة المفتوحة باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لاستخدام ميزات Open Type في Aspose.Words لـ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن العمل مع ميزات Open Type في مستندات Word الخاصة بك.

توفر ميزات Open Type إمكانات محسنة للطباعة وتشكيل النص، مما يسمح لك بإنشاء مستندات جذابة بصريًا وذات مظهر احترافي. قم بتجربة مصانع مختلفة لتشكيل النص واستكشف إمكانيات ميزات Open Type في مشاريعك.

### الأسئلة الشائعة

#### س: كيف يمكنني تمكين ميزات OpenType في Aspose.Words لـ .NET؟

ج: لتمكين ميزات OpenType في Aspose.Words لـ .NET، يتعين عليك اتباع الخطوات المذكورة في البرنامج التعليمي.

#### س: ما هي ميزات OpenType المدعومة في Aspose.Words لـ .NET؟

ج: يدعم Aspose.Words for .NET العديد من ميزات OpenType، مثل الحروف المركبة، وتنوعات الحروف الرسومية، والبدائل السياقية، والمزيد.

#### س: كيف يمكنني التحقق مما إذا كانت ميزة OpenType مدعومة في خط معين؟

ج: يمكنك التحقق مما إذا كانت ميزة OpenType مدعومة في خط معين باستخدام ملف`Font.OpenTypeFeatures` الطريقة في Aspose.Words لـ .NET.

#### س: ما هي ميزات تنسيق النص الأخرى التي يدعمها Aspose.Words for .NET؟

ج: بصرف النظر عن ميزات OpenType، يدعم Aspose.Words for .NET أيضًا ميزات تنسيق النص الأخرى مثل تنسيق الفقرات وإنشاء الجداول وإضافة الصور وما إلى ذلك.

#### س: هل يمكنني استخدام ميزات OpenType في كافة إصدارات Aspose.Words لـ .NET؟

ج: يتم دعم ميزات OpenType في الإصدارات الأحدث من Aspose.Words لـ .NET. تأكد من أنك تستخدم إصدارًا متوافقًا للاستفادة من هذه الميزات.