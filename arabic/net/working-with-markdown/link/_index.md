---
title: وصلة
linktitle: وصلة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الروابط مع Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/link/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة الروابط مع Aspose.Words for .NET. تُستخدم الروابط لإنشاء مراجع قابلة للنقر لمواقع الويب أو المستندات الأخرى.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة الثانية: إدخال ارتباط

 يمكننا إدراج ارتباط باستخدام ملف`Insertlink` طريقة منشئ الوثيقة. نحتاج إلى تحديد نص الرابط ، هنا "Aspose" ، بالإضافة إلى عنوان URL المقصود.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com "، خطأ) ؛
```

### مثال على شفرة المصدر للروابط مع Aspose.Words for .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// أدخل ارتباط.
builder.Insertlink("Aspose", "https://www.aspose.com "، خطأ) ؛
```
تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الروابط مع Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكنني الارتباط بعنوان URL في Aspose.Words؟

 ج: للارتباط بعنوان URL في Aspose.Words ، يمكنك استخدام`<a>` علامة مع`href` السمة التي تحتوي على عنوان URL. على سبيل المثال ، يمكنك استخدام ملفات`<a href="https://www.aspose.com">Click Here</a>` للارتباط التشعبي إلى عنوان URL "https://www.example.com" مع النص المعروض "انقر هنا".

#### س: هل من الممكن الارتباط بإشارة مرجعية داخلية في Aspose.Words؟

 ج: نعم ، من الممكن الربط بإشارة مرجعية داخلية في Aspose.Words. يمكنك استخدام ال`<a>` علامة مع`href` السمة التي تحتوي على اسم الإشارة مسبوقة بعلامة تجزئة (#). على سبيل المثال،`<a href="#bookmark1">Go to bookmark 1</a>` سيرتبط بالإشارة المرجعية المسماة "bookmark1" في المستند.

#### س: كيف يمكنني تخصيص نص عرض الارتباط في Aspose.Words؟

ج: لتخصيص نص عرض الارتباط في Aspose.Words ، يمكنك تعديل المحتوى بين`<a>` العلامات. على سبيل المثال،`<a href="https://www.aspose.com">Click here</a>` سيعرض النص "انقر هنا" كارتباط تشعبي.

#### س: هل يمكنني تحديد هدف لارتباط في Aspose.Words؟

 ج: نعم ، يمكنك تحديد هدف لارتباط في Aspose. Words باستخدام`target` سمة من سمات`<a>` بطاقة شعار. على سبيل المثال،`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` سيفتح الرابط في نافذة أو علامة تبويب جديدة.