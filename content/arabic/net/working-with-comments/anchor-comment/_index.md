---
title: تعليق مرساة
linktitle: تعليق مرساة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة التعليقات الأساسية في مستندات Word باستخدام Aspose.Words لـ .NET. اتبع دليلنا خطوة بخطوة للتعاون الفعال في المستندات.
type: docs
weight: 10
url: /ar/net/working-with-comments/anchor-comment/
---
## مقدمة

هل سبق لك أن وجدت نفسك في موقف حيث كنت بحاجة إلى إضافة تعليقات على أقسام نصية معينة في مستند Word برمجياً؟ تخيل أنك تتعاون في مستند مع فريقك، وتحتاج إلى تسليط الضوء على أجزاء معينة بالتعليقات ليقوم الآخرون بمراجعتها. في هذا البرنامج التعليمي، سنتعمق في كيفية إدراج التعليقات الأساسية في مستندات Word باستخدام Aspose.Words for .NET. سنقوم بتقسيم العملية إلى خطوات بسيطة، مما يسهل عليك متابعة مشاريعك وتنفيذها.

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من أن لديك كل ما تحتاجه:

-  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: أي بيئة تطوير .NET مثل Visual Studio.
- الفهم الأساسي لـ C#: الإلمام ببرمجة C# سيساعدك على اتباع الخطوات بسهولة.

الآن، دعنا نتعمق في مساحات الأسماء التي ستحتاج إلى استيرادها لهذه المهمة.

## استيراد مساحات الأسماء

للبدء، تأكد من استيراد مساحات الأسماء الضرورية في مشروعك. فيما يلي مساحات الأسماء المطلوبة:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.CommentRangeStart;
using Aspose.Words.CommentRangeEnd;
```

بعد الانتهاء من المتطلبات الأساسية ومساحات الأسماء، دعنا ننتقل إلى الجزء الممتع: تقسيم العملية خطوة بخطوة.

## الخطوة 1: إنشاء مستند جديد

أولاً، لنقم بإنشاء مستند Word جديد. سيكون هذا بمثابة لوحة قماشية لتعليقاتنا.

```csharp
// حدد الدليل الذي سيتم حفظ المستند فيه
string dataDir = "YOUR DOCUMENT DIRECTORY";        

// قم بإنشاء مثيل لفئة المستند
Document doc = new Document();
```

 في هذه الخطوة، نقوم بتهيئة ملف جديد`Document` الكائن الذي سيتم استخدامه لإضافة تعليقاتنا.

## الخطوة 2: إضافة نص إلى المستند

بعد ذلك، سنقوم بإضافة بعض النص إلى المستند. سيكون هذا النص هو الهدف لتعليقاتنا.

```csharp
// إنشاء الفقرة الأولى وتشغيلها
Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

// قم بإنشاء الفقرة الثانية وتشغيلها
Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

 هنا، نقوم بإنشاء فقرتين مع بعض النص. يتم تغليف كل جزء من النص في ملف`Run` الكائن، والذي يتم إضافته بعد ذلك إلى الفقرات.

## الخطوة 3: إنشاء تعليق

الآن، دعونا ننشئ تعليقًا سنرفقه بالنص.

```csharp
// إنشاء تعليق جديد
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

 في هذه الخطوة نقوم بإنشاء`Comment` كائن وإضافة فقرة وتشغيل مع نص التعليق.

## الخطوة 4: تحديد نطاق التعليق

لربط التعليق بنص معين، نحتاج إلى تحديد بداية ونهاية نطاق التعليق.

```csharp
// تحديد CommentRangeStart وCommentRangeEnd
CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

// أدخل CommentRangeStart وCommentRangeEnd في المستند
run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);

// أضف التعليق إلى المستند
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

 هنا نخلق`CommentRangeStart`و`CommentRangeEnd` الكائنات، وربطها بالتعليق بواسطة معرفها. نقوم بعد ذلك بإدراج هذه النطاقات في المستند، مما يؤدي إلى تثبيت تعليقنا بشكل فعال على النص المحدد.

## الخطوة 5: احفظ المستند

أخيرًا، لنحفظ مستندنا في الدليل المحدد.

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

تقوم هذه الخطوة بحفظ المستند الذي يحتوي على التعليق المرتبط في الدليل المحدد.

## خاتمة

وهنا لديك! لقد تعلمت بنجاح كيفية إضافة تعليقات الربط إلى أقسام نصية محددة في مستند Word باستخدام Aspose.Words for .NET. تعتبر هذه التقنية مفيدة بشكل لا يصدق للتعاون في المستندات، مما يسمح لك بإبراز أجزاء معينة من النص والتعليق عليها بسهولة. سواء كنت تعمل على مشروع مع فريقك أو تراجع المستندات، ستعمل هذه الطريقة على تحسين إنتاجيتك وتبسيط سير عملك.

## الأسئلة الشائعة

### ما هو الغرض من استخدام التعليقات المرساة في مستندات Word؟
تُستخدم التعليقات الأساسية لتمييز أقسام معينة من النص والتعليق عليها، مما يسهل تقديم التعليقات والتعاون في المستندات.

### هل يمكنني إضافة تعليقات متعددة إلى نفس قسم النص؟
نعم، يمكنك إضافة تعليقات متعددة إلى قسم النص نفسه عن طريق تحديد نطاقات تعليقات متعددة.

### هل Aspose.Words لـ .NET مجاني للاستخدام؟
يقدم Aspose.Words for .NET نسخة تجريبية مجانية يمكنك تنزيلها[هنا](https://releases.aspose.com/) . للحصول على الميزات الكاملة، يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy).

### هل يمكنني تخصيص مظهر التعليقات؟
بينما يركز Aspose.Words على الوظائف، يتم التحكم بشكل عام في مظهر التعليقات في مستندات Word بواسطة Word نفسه.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Words لـ .NET؟
 يمكنك العثور على وثائق مفصلة[هنا](https://reference.aspose.com/words/net/).