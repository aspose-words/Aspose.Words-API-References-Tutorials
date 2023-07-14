---
title: ربط تلقائي
linktitle: ربط تلقائي
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الارتباط التلقائي مع Aspose.Words دليل تفصيلي خطوة بخطوة لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-markdown/autolink/
---

في هذا المثال ، سنشرح كيفية استخدام ميزة "الربط التلقائي" مع Aspose.Words for .NET. تتيح لك هذه الميزة إدراج ارتباطات تشعبية في المستند تلقائيًا.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إدراج ارتباط تشعبي

 يمكننا إدراج ارتباط تشعبي باستخدام الامتداد`InsertHyperlink` طريقة منشئ الوثيقة. نحدد عنوان URL والنص الذي سيتم عرضه للرابط.

```csharp
builder.InsertHyperlink("https://www.aspose.com "،" https://www.aspose.com "، خطأ) ؛
```

## الخطوة 3: إدخال عنوان بريد إلكتروني كرابط

يمكننا أيضًا إدخال عنوان بريد إلكتروني كارتباط باستخدام البادئة "mailto:". سيسمح هذا للمستخدمين بالنقر فوق الارتباط لفتح عميل البريد الإلكتروني الافتراضي الخاص بهم.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## الخطوة 4: حفظ المستند

أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب.

### مثال على كود المصدر للربط التلقائي باستخدام Aspose.Words for .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// أدخل ارتباط تشعبي.
builder.InsertHyperlink("https://www.aspose.com "،" https://www.aspose.com "، خطأ) ؛
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة "الربط التلقائي" مع Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكنني إنشاء ارتباط تلقائي بعنوان URL في Aspose.Words؟

 ج: لإنشاء ارتباط تلقائي بعنوان URL في Aspose.Words ، يمكنك استخدام`<a>` علامة مع`href` السمة التي تحتوي على عنوان URL. على سبيل المثال ، يمكنك استخدام ملفات`<a href="https://www.aspose.com">https://www.aspose.com</a>` للربط تلقائيًا بـ "https: //www.aspose.com".

#### س: هل من الممكن تخصيص نص العرض للارتباط التلقائي في Aspose.Words؟

 ج: نعم ، يمكنك تخصيص نص العرض للارتباط التلقائي في Aspose.Words. بدلاً من استخدام عنوان URL كنص عرض ، يمكنك استخدام أي نص آخر عن طريق استبدال المحتوى بين`<a>` العلامات. على سبيل المثال ، يمكنك استخدام ملفات`<a href="https://www.aspose.com">Click here</a>` لعرض النص "انقر هنا" كارتباط تلقائي.

#### س: كيف يمكنني إضافة سمات إضافية إلى ارتباط تلقائي في Aspose.Words؟

ج: لإضافة سمات إضافية إلى ارتباط تلقائي في Aspose.Words ، يمكنك استخدام سمات HTML إضافية داخل ملف`<a>` بطاقة شعار. على سبيل المثال ، يمكنك استخدام ملفات`<a href="https://www.aspose.com" target="_blank">Link</a>` لفتح الرابط في نافذة أو علامة تبويب جديدة باستخدام ملف` attribute target="_blank"`.