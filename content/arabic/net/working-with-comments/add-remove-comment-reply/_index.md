---
title: إضافة إزالة التعليق الرد
linktitle: إضافة إزالة التعليق الرد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة ردود التعليقات وإزالتها في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/add-remove-comment-reply/
---

في هذا البرنامج التعليمي الشامل، سوف تتعلم كيفية إضافة وإزالة ردود التعليقات في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إدارة ردود التعليقات وتخصيصها وفقًا لمتطلباتك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: قم بتحميل المستند
للبدء، قم بتحميل المستند الذي يحتوي على التعليقات باستخدام فئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## الخطوة 2: الوصول إلى التعليق وإدارة الردود
بعد ذلك، قم بالوصول إلى التعليق من المستند باستخدام طريقة GetChild مع المعلمة NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

لإزالة رد من التعليق، استخدم طريقة RemoveReply وقم بتوفير فهرس الرد المطلوب:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

لإضافة رد جديد على التعليق، استخدم الأسلوب AddReply وقم بتوفير اسم المؤلف والأحرف الأولى من اسم المؤلف والتاريخ والوقت ونص الرد:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## الخطوة 3: احفظ المستند
بعد إضافة ردود التعليقات أو إزالتها، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### مثال على التعليمات البرمجية المصدر لإضافة وإزالة ردود التعليقات باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإضافة وإزالة ردود التعليقات باستخدام Aspose.Words لـ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة ردود التعليقات وإزالتها في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن إدارة ردود التعليقات وتخصيصها وفقًا لمتطلباتك.

تسمح ردود التعليقات بإجراء مناقشات تعاونية وملاحظات داخل المستند. قم بالتجربة مع مؤلفي الرد والأحرف الأولى والتواريخ والنصوص المختلفة لتعزيز التعاون والتواصل داخل مستنداتك.

### الأسئلة الشائعة

#### س: كيف يمكنني إضافة تعليق في Aspose.Words لـ .NET؟

 ج: لإضافة تعليق في Aspose.Words لـ .NET، يمكنك استخدام`Comment.AddComment` طريقة تحدد نص التعليق والمكان الذي تريد إضافته في المستند.

#### س: كيف يمكنني إزالة تعليق في Aspose.Words لـ .NET؟

 ج: لإزالة تعليق في Aspose.Words لـ .NET، يمكنك استخدام`Comment.Remove` طريقة تحديد`Comment` الكائن الذي تريد إزالته.

#### س: هل يمكنني الرد على تعليق في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك الرد على تعليق في Aspose.Words for .NET باستخدام`Comment.AddReply` طريقة تحدد نص الرد والمكان الذي تريد إضافته في المستند.

#### س: كيف يمكنني الوصول إلى التعليقات الموجودة في Aspose.Words لـ .NET؟

 ج: يمكنك الوصول إلى التعليقات الموجودة في Aspose.Words for .NET باستخدام`CommentCollection` ملكية`Document`هدف. سيسمح لك هذا بتصفح جميع التعليقات الموجودة في المستند.

#### س: هل يمكنني تحرير نص التعليق في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك تحرير نص التعليق في Aspose.Words for .NET عن طريق الوصول إلى`Comment.Text` خاصية المقابلة`Comment` الكائن وتعديل النص حسب الحاجة.