---
title: أضف التعليقات
linktitle: أضف التعليقات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة تعليقات إلى مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-comments/add-comments/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إضافة تعليقات إلى مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إدراج التعليقات وتخصيص محتواها في مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة الثانية: إضافة محتوى إلى المستند
بعد ذلك ، أضف المحتوى المطلوب إلى المستند باستخدام كائن DocumentBuilder. في هذا المثال ، نضيف بعض النصوص:

```csharp
builder.Write("Some text is added.");
```

## الخطوة 3: قم بإنشاء تعليق وإضافة محتويات
لإضافة تعليق ، قم بإنشاء مثيل للفئة Comment ، وتمرير كائن Document ، واسم المؤلف ، والأحرف الأولى للمؤلف ، والتاريخ الحالي:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

بعد ذلك ، قم بإلحاق التعليق بالفقرة الحالية:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

أضف محتويات إلى التعليق ، مثل فقرة ونص:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## الخطوة 4: احفظ المستند
بعد إضافة التعليق ومحتوياته ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## مثال كود المصدر لإضافة تعليقات باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإضافة التعليقات باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة تعليقات إلى مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إدراج التعليقات وتخصيص محتواها في مستنداتك.

التعليقات مفيدة للتعاون أو توفير معلومات إضافية أو تدوين الملاحظات داخل المستند. جرب أسماء مؤلفين مختلفة وأحرف أولى ومحتويات تعليق لتلبية متطلباتك المحددة.