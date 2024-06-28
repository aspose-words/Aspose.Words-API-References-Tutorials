---
title: وصلة
linktitle: وصلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج روابط باستخدام Aspose.Words لـ .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/link/
---

في هذا المثال، سنرشدك إلى كيفية استخدام ميزة الروابط مع Aspose.Words for .NET. تُستخدم الروابط لإنشاء مراجع قابلة للنقر عليها لمواقع الويب أو المستندات الأخرى.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إدراج رابط

 يمكننا إدراج رابط باستخدام`InsertHyperlink` طريقة مولد الوثيقة. نحتاج إلى تحديد نص الرابط، هنا "Apose"، بالإضافة إلى عنوان URL المقصود.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com"، خطأ)؛
```

### مثال على التعليمات البرمجية المصدر للارتباطات مع Aspose.Words لـ .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// أدخل الرابط.
builder.InsertHyperlink("Aspose", "https://www.aspose.com"، خطأ)؛
```
تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الروابط مع Aspose.Words لـ .NET.


### الأسئلة الشائعة

#### س: كيف يمكنني الارتباط بعنوان URL في Aspose.Words؟

 ج: للارتباط بعنوان URL في Aspose.Words، يمكنك استخدام`<a>` العلامة مع`href` السمة التي تحتوي على عنوان URL. على سبيل المثال، يمكنك استخدام`<a href="https://www.aspose.com">Click Here</a>` للارتباط التشعبي بعنوان URL "https://www.example.com" مع نص العرض "انقر هنا".

#### س: هل من الممكن الارتباط بإشارة مرجعية داخلية في Aspose.Words؟

 ج: نعم، من الممكن الارتباط بإشارة مرجعية داخلية في Aspose.Words. يمكنك استخدام ال`<a>` العلامة مع`href` سمة تحتوي على اسم الإشارة المرجعية مسبوقة بالعلامة (#). على سبيل المثال،`<a href="#bookmark1">Go to bookmark 1</a>` سيتم الارتباط بالإشارة المرجعية المسماة "bookmark1" في المستند.

#### س: كيف يمكنني تخصيص نص العرض الخاص بالارتباط في Aspose.Words؟

ج: لتخصيص نص عرض الرابط في Aspose.Words، يمكنك تعديل المحتوى بين`<a>` العلامات. على سبيل المثال،`<a href="https://www.aspose.com">Click here</a>` سيعرض النص "انقر هنا" كارتباط تشعبي.

#### س: هل يمكنني تحديد هدف لارتباط في Aspose.Words؟

 ج: نعم، يمكنك تحديد هدف للارتباط في Aspose.Words باستخدام الأمر`target` سمة من`<a>` بطاقة شعار. على سبيل المثال،`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` سيفتح الرابط في نافذة أو علامة تبويب جديدة.