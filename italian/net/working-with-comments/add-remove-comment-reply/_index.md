---
title: إضافة إزالة التعليق الرد
linktitle: إضافة إزالة التعليق الرد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إضافة وإزالة الردود على التعليقات في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/add-remove-comment-reply/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إضافة ردود التعليقات وإزالتها في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على إدارة ردود التعليقات وتخصيصها وفقًا لمتطلباتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بتحميل المستند
للبدء ، قم بتحميل المستند الذي يحتوي على التعليقات باستخدام فئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## الخطوة 2: الوصول إلى التعليق وإدارة الردود
بعد ذلك ، قم بالوصول إلى التعليق من المستند باستخدام طريقة GetChild مع معلمة NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

لإزالة رد من التعليق ، استخدم طريقة RemoveReply وقم بتوفير فهرس الرد المطلوب:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

لإضافة رد جديد على التعليق ، استخدم طريقة AddReply وقم بتوفير اسم المؤلف والأحرف الأولى من اسم المؤلف والتاريخ والوقت ونص الرد:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## الخطوة 3: احفظ المستند
بعد إضافة الردود على التعليقات أو إزالتها ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### مثال على كود المصدر لإضافة وإزالة التعليقات باستخدام Aspose.Words for .NET
إليك الكود المصدري الكامل لإضافة وإزالة الردود على التعليقات باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة وإزالة الردود على التعليقات في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام الكود المصدري المقدم ، يمكنك الآن إدارة ردود التعليقات وتخصيصها وفقًا لمتطلباتك.

تسمح الردود على التعليقات بالمناقشات التعاونية والتعليقات داخل المستند. جرّب مؤلفي الردود المختلفين والأحرف الأولى والتواريخ والنصوص لتعزيز التعاون والتواصل داخل مستنداتك.