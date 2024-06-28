---
title: تعليق مرساة
linktitle: تعليق مرساة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ربط ردود التعليقات على نص محدد في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/anchor-comment/
---

في هذا البرنامج التعليمي الشامل، ستتعلم كيفية ربط ردود التعليقات على نص محدد في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من ربط التعليقات بنص محدد في مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد وإضافة نص
للبدء، قم بإنشاء مستند جديد باستخدام فئة المستند وأضف النص المطلوب:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## الخطوة 2: إنشاء تعليق وإضافة نطاق التعليق
بعد ذلك، قم بإنشاء تعليق وربطه بنص محدد باستخدام كائنات CommentRangeStart وCommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## الخطوة 3: احفظ المستند
بعد ربط التعليق بنص محدد، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### مثال على الكود المصدري للرد على تعليق الارتساء باستخدام Aspose.Words لـ .NET
فيما يلي كود المصدر الكامل لتثبيت الرد على التعليق باستخدام Aspose.Words for .NET:

```csharp
// إنشاء مثيل للمستند.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// قم بإنشاء ثلاثة كائنات تشغيل.
//يقوم الأولان بتشغيل بعض النصوص، بينما يقوم الثالث بتشغيل تعليق

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// يحتوي كل كائن من كائنات التشغيل على كائنين CommentRangeStart وCommentRangeEnd مقترنين.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### الأسئلة الشائعة

#### س: ما هو مرساة التعليق في Aspose.Words لـ .NET؟

ج: في Aspose.Words for .NET، يعتبر رابط التعليق بمثابة علامة تربط التعليق بموقع محدد في المستند.

#### س: كيف يمكنني إضافة رابط تعليق في مستند Aspose.Words for .NET؟

ج: لإضافة رابط تعليق في مستند Aspose.Words for .NET، اتبع الخطوات المذكورة في البرنامج التعليمي.

#### س: كيف يمكنني الوصول إلى نقطة ارتساء التعليق الموجودة في Aspose.Words لـ .NET؟

 ج: يمكنك الوصول إلى رابط التعليق الموجود في Aspose.Words لـ .NET باستخدام`Comment.Anchor` ملكية.

#### س: هل يمكنني إضافة رابط تعليق في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك إزالة رابط التعليق في Aspose.Words لـ .NET باستخدام`Comment.Remove` طريقة.

#### س: كيف يمكنني تحرير نص التعليق المرتبط بنقطة ارتساء التعليق في Aspose.Words لـ .NET؟

ج: لتعديل نص التعليق المنضم إلى رابط التعليق في Aspose.Words لـ .NET، يمكنك الوصول إلى`Comment.Text` خاصية المقابلة`Comment` كائن وتعديل النص حسب الحاجة.

