---
title: فتح ميزات النوع
linktitle: فتح ميزات النوع
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words for .NET
type: docs
weight: 10
url: /de/net/enable-opentype-features/open-type-features/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من العمل باستخدام ميزات Open Type في مستندات Word الخاصة بك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بتحميل المستند
للبدء ، قم بتحميل المستند باستخدام فئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## الخطوة 2: تفعيل ميزات النوع المفتوح
لتمكين ميزات Open Type ، قم بتعيين خاصية TextShaperFactory لفئة LayoutOptions على مثيل لمصنع شكل النص المطلوب. في هذا المثال ، نستخدم HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## الخطوة 3: احفظ المستند
بعد تمكين ميزات Open Type ، احفظ المستند بتنسيق الإخراج المطلوب ، مثل PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### مثال على كود المصدر لميزات النوع المفتوح باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لاستخدام ميزات Open Type في Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تمكين ميزات Open Type واستخدامها في Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن العمل مع ميزات Open Type في مستندات Word الخاصة بك.

توفر ميزات Open Type إمكانات طباعة وتشكيل نصية محسّنة ، مما يسمح لك بإنشاء مستندات جذابة بصريًا وذات مظهر احترافي. جرب مصانع مختلفة لأشكال النص واستكشف إمكانيات ميزات Open Type في مشروعاتك.
