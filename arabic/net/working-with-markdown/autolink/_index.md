---
title: ربط تلقائي
linktitle: ربط تلقائي
second_title: Aspose.Words لمراجع .NET API
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

//أدخل ارتباط تشعبي.
builder.InsertHyperlink("https://www.aspose.com "،" https://www.aspose.com "، خطأ) ؛
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة "الربط التلقائي" مع Aspose.Words for .NET.

