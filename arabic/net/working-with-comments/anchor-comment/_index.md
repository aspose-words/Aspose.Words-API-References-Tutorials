---
title: تعليق المرساة
linktitle: تعليق المرساة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إرساء ردود التعليقات على نص معين في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/anchor-comment/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إرساء ردود التعليقات على نص معين في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من ربط التعليقات بنص محدد في مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد وإضافة نص
للبدء ، أنشئ مستندًا جديدًا باستخدام فئة المستند وأضف النص المطلوب:

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

## الخطوة 2: قم بإنشاء تعليق وإضافة نطاق تعليق
بعد ذلك ، قم بإنشاء تعليق واربطه بنص معين باستخدام كائني CommentRangeStart و CommentRangeEnd:

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
بعد إرساء التعليق على نص معين ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### مثال رمز مصدر للتعليق المرساة الرد باستخدام Aspose.Words for .NET
إليك الكود المصدري الكامل لترسيخ الرد على التعليق باستخدام Aspose.Words for .NET:

```csharp
// قم بإنشاء مثيل من المستند.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// إنشاء ثلاثة كائنات تشغيل.
//يقوم أول اثنان بتشغيل بعض النصوص ، بينما يقوم الثالث بتشغيل تعليق

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

// يحتوي كل كائن تشغيل على كائن CommentRangeStart و CommentRangeEnd مرتبط.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### التعليمات

#### س: ما هو تعليق التعليق في Aspose.Words لـ .NET؟

ج: في Aspose.Words for .NET ، رابط التعليق هو علامة تربط تعليق بموقع معين في مستند.

#### س: كيف يمكنني إضافة رابط تعليق في مستند Aspose.Words for .NET؟

ج: لإضافة رابط تعليق في مستند Aspose.Words for .NET ، اتبع الخطوات المذكورة في البرنامج التعليمي.

#### س: كيف يمكنني الوصول إلى رابط تعليق موجود في Aspose.Words for .NET؟

 ج: يمكنك الوصول إلى رابط تعليق موجود في Aspose.Words for .NET باستخدام`Comment.Anchor` ملكية.

#### س: هل يمكنني توفير مذيع تعليق في Aspose.Words for .NET؟

 ج: نعم ، يمكنك إزالة رابط التعليق في Aspose.Words for .NET باستخدام`Comment.Remove` طريقة.

#### س: كيف يمكنني تعديل نص تعليق مرتبط بأحد ارتساء التعليقات في Aspose.Words for .NET؟

ج: لتعديل نص تعليق مرتبط بإرساء تعليق في Aspose.Words for .NET ، يمكنك الوصول إلى`Comment.Text` الممتلكات المقابلة`Comment` الكائن وتعديل النص حسب الحاجة.

