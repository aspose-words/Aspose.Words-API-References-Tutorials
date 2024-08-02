---
title: الارتباط التلقائي
linktitle: الارتباط التلقائي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الارتباط التلقائي باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/autolink/
---

في هذا المثال، سنشرح كيفية استخدام ميزة "الارتباط التلقائي" مع Aspose.Words لـ .NET. تتيح لك هذه الميزة إدراج الارتباطات التشعبية في المستند تلقائيًا.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إدراج ارتباط تشعبي

 يمكننا إدراج رابط تشعبي باستخدام`InsertHyperlink` طريقة مولد الوثيقة. نحدد عنوان URL والنص الذي سيتم عرضه للارتباط.

```csharp
builder.InsertHyperlink("https://www.aspose.com"، "https://www.aspose.com"، خطأ)؛
```

## الخطوة 3: إدراج عنوان بريد إلكتروني كرابط

يمكننا أيضًا إدراج عنوان بريد إلكتروني كرابط باستخدام البادئة "mailto:". سيسمح هذا للمستخدمين بالنقر فوق الرابط لفتح عميل البريد الإلكتروني الافتراضي الخاص بهم.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## الخطوة 4: حفظ الوثيقة

وأخيرا، يمكننا حفظ المستند بالتنسيق المطلوب.

### مثال على كود المصدر للارتباط التلقائي باستخدام Aspose.Words لـ .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// إدراج ارتباط تشعبي.
builder.InsertHyperlink("https://www.aspose.com"، "https://www.aspose.com"، خطأ)؛
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة "الارتباط التلقائي" مع Aspose.Words لـ .NET.


### الأسئلة الشائعة

#### س: كيف يمكنني إنشاء رابط تلقائي لعنوان URL في Aspose.Words؟

 ج: لإنشاء رابط تلقائي لعنوان URL في Aspose.Words، يمكنك استخدام`<a>` العلامة مع`href` السمة التي تحتوي على عنوان URL. على سبيل المثال، يمكنك استخدام`<a href="https://www.aspose.com">https://www.aspose.com</a>` للارتباط تلقائيًا بـ "https: //www.aspose.com".

#### س: هل من الممكن تخصيص نص العرض للارتباط التلقائي في Aspose.Words؟

 ج: نعم، يمكنك تخصيص نص العرض للارتباط التلقائي في Aspose.Words. بدلاً من استخدام عنوان URL كنص العرض، يمكنك استخدام أي نص آخر عن طريق استبدال المحتوى بين`<a>` العلامات. على سبيل المثال، يمكنك استخدام`<a href="https://www.aspose.com">Click here</a>`لعرض النص "انقر هنا" كرابط تلقائي.

#### س: كيف يمكنني إضافة سمات إضافية إلى الارتباط التلقائي في Aspose.Words؟

 ج: لإضافة سمات إضافية إلى رابط تلقائي في Aspose.Words، يمكنك استخدام سمات HTML إضافية داخل`<a>` بطاقة شعار. على سبيل المثال، يمكنك استخدام`<a href="https://www.aspose.com" target="_blank">Link</a>` لفتح الرابط في نافذة أو علامة تبويب جديدة باستخدام` attribute target="_blank"`.