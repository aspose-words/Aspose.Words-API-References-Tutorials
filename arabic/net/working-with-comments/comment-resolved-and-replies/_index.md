---
title: حل التعليق والردود
linktitle: حل التعليق والردود
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية حل التعليقات والردود عليها في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/comment-resolved-and-replies/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية حل التعليقات والردود عليها في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على إدارة حل التعليقات وتحديث حالة التعليقات والردود عليها.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بتحميل المستند والوصول إلى التعليقات
للبدء ، قم بتحميل المستند الذي يحتوي على التعليقات باستخدام فئة المستند والوصول إلى مجموعة التعليقات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## الخطوة 2: حل التعليقات والردود عليها
بعد ذلك ، كرر التعليقات والردود عليها لتمييزها على أنها تم الحل:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

في الكود أعلاه ، نصل إلى تعليق الوالدين ونكرره من خلال ردوده. يمكننا استرداد معرف التعليق الأصلي وحالة حلها. بعد ذلك ، نقوم بتحديث علامة "تم" لكل رد على التعليق للإشارة إلى الحل.

## الخطوة 3: احفظ المستند
بعد حل التعليقات وتحديث حالتها ، احفظ المستند المعدل في ملف باستخدام طريقة Save من فئة Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### مثال على كود المصدر لحل التعليقات والردود عليها باستخدام Aspose.Words for .NET
إليك التعليمات البرمجية المصدر الكاملة لحل التعليقات والردود عليها باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
تذكر أن تقوم بضبط الكود وفقًا لمتطلباتك المحددة ، بما في ذلك مسار ملف المستند والتخصيص الإضافي

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية حل التعليقات والردود عليها في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إدارة حل التعليقات وتحديث حالة التعليقات وردودها وفقًا لمتطلباتك.

يساعد حل التعليق في تعقب الملاحظات وإدارتها داخل المستند. جرب حالات تعليق مختلفة وقم بتخصيصها لتحسين التعاون وعمليات المراجعة في مستنداتك.

### التعليمات

#### س: كيف يمكنني حل تعليق في Aspose.Words for .NET؟

 ج: لحل تعليق في Aspose.Words for .NET ، يمكنك استخدام`Comment.Resolve` طريقة تحديد`Comment` الكائن الذي تريد حله. سيؤدي هذا إلى وضع علامة على التعليق على أنه تم حله وإخفائه في المستند النهائي.

#### س: كيف يمكنني إضافة رد على تعليق تم حله في Aspose.Words for .NET؟

 ج: على الرغم من إخفاء التعليقات التي تم حلها افتراضيًا في المستند النهائي ، لا يزال بإمكانك إضافة رد على تعليق تم حله باستخدام`Comment.AddReply` طريقة تحدد نص الرد والمكان الذي تريد إضافته فيه.

#### س: كيف يمكنني عرض التعليقات التي تم حلها في Aspose.Words for .NET؟

 ج: بشكل افتراضي ، يتم إخفاء التعليقات التي تم حلها في المستند النهائي. ومع ذلك ، يمكنك إظهارها باستخدام ملف`CommentOptions.ShowResolvedComments` ممتلكات`Document` الاعتراض وضبطه على`true`.

#### س: كيف يمكنني إخفاء كل التعليقات ، بما في ذلك الردود ، في Aspose.Words for .NET؟

 ج: لإخفاء جميع التعليقات ، بما في ذلك الردود ، في Aspose.Words for .NET ، يمكنك استخدام`CommentOptions.CommentDisplayMode` ممتلكات`Document` كائن وضبطه على`CommentDisplayMode.None`.

#### س: هل يمكنني تعديل نص تعليق تم حله في Aspose.Words for .NET؟

 ج: نعم ، يمكنك تعديل نص تعليق تم حله في Aspose.Words for .NET من خلال الوصول إلى`Comment.Text` الممتلكات المقابلة`Comment` الكائن وتعديل النص حسب الحاجة.