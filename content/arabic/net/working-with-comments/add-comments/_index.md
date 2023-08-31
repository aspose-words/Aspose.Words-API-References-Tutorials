---
title: أضف تعليقات
linktitle: أضف تعليقات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة تعليقات إلى مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/add-comments/
---

في هذا البرنامج التعليمي الشامل، ستتعلم كيفية إضافة تعليقات إلى مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إدراج التعليقات وتخصيص محتواها في مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد وDocumentBuilder
للبدء، قم بإنشاء مستند جديد باستخدام فئة Document وقم بتهيئة كائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إضافة محتوى إلى المستند
بعد ذلك، قم بإضافة المحتوى المطلوب إلى المستند باستخدام كائن DocumentBuilder. في هذا المثال، نضيف بعض النص:

```csharp
builder.Write("Some text is added.");
```

## الخطوة 3: إنشاء تعليق وإضافة محتويات
لإضافة تعليق، قم بإنشاء مثيل لفئة التعليق، وقم بتمرير كائن المستند، واسم المؤلف، والأحرف الأولى من اسم المؤلف، والتاريخ الحالي:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

بعد ذلك، قم بإلحاق التعليق بالفقرة الحالية:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

إضافة محتويات إلى التعليق، مثل فقرة ونص:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## الخطوة 4: احفظ المستند
بعد إضافة التعليق ومحتوياته، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## مثال على كود المصدر لإضافة تعليقات باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإضافة التعليقات باستخدام Aspose.Words لـ .NET:

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
تهانينا! لقد تعلمت بنجاح كيفية إضافة التعليقات إلى مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن إدراج التعليقات وتخصيص محتواها في مستنداتك.

تعد التعليقات مفيدة للتعاون أو تقديم معلومات إضافية أو تدوين الملاحظات داخل المستند. قم بتجربة أسماء المؤلفين والأحرف الأولى ومحتويات التعليقات المختلفة لتلبية متطلباتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني إضافة تعليق في مستند Aspose.Words for .NET؟

ج: لإضافة تعليق في مستند Aspose.Words for .NET، يتعين عليك اتباع الخطوات المذكورة في البرنامج التعليمي.

#### س: هل يمكنني تنسيق نص التعليق في Aspose.Words لـ .NET؟

ج: نعم، يمكنك تنسيق نص التعليق في Aspose.Words لـ .NET باستخدام خصائص التنسيق المتاحة.

#### س: كيف يمكنني استرداد جميع التعليقات الموجودة في المستند؟

ج: يمكنك استرداد جميع التعليقات الموجودة في المستند باستخدام الملف`Document.Comments` ملكية.

#### س: هل يمكنني حذف تعليق محدد في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك إزالة تعليق محدد في Aspose.Words لـ .NET باستخدام`Comment.Remove` طريقة.

#### س: كيف يمكنني تعديل نص التعليق الموجود في Aspose.Words لـ .NET؟

 ج: لتعديل نص تعليق موجود في Aspose.Words لـ .NET، يمكنك الوصول إلى`Comment.Text` خاصية المقابلة`Comment` كائن وتعديل النص حسب الحاجة.