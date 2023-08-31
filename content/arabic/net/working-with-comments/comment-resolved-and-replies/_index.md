---
title: تم حل التعليق والردود
linktitle: تم حل التعليق والردود
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية حل التعليقات والردود عليها في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-comments/comment-resolved-and-replies/
---

في هذا البرنامج التعليمي الشامل، ستتعلم كيفية حل التعليقات والردود عليها في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إدارة دقة التعليقات وتحديث حالة التعليقات والردود عليها.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: قم بتحميل المستند والوصول إلى التعليقات
للبدء، قم بتحميل المستند الذي يحتوي على التعليقات باستخدام فئة المستند وقم بالوصول إلى مجموعة التعليقات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## الخطوة 2: حل التعليقات وردودها
بعد ذلك، قم بمراجعة التعليقات وردودها لوضع علامة "تم الحل" عليها:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

في الكود أعلاه، نصل إلى تعليق الوالدين ونكرر ردوده. يمكننا استرداد معرف التعليق الأصلي وحالة الحل الخاصة به. بعد ذلك، نقوم بتحديث علامة "تم" الخاصة بكل رد على التعليق للإشارة إلى الحل.

## الخطوة 3: احفظ المستند
بعد حل التعليقات وتحديث حالتها، احفظ المستند المعدل في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### مثال على كود المصدر لحل التعليقات والردود عليها باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لحل التعليقات والردود عليها باستخدام Aspose.Words for .NET:

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
تذكر أن تقوم بضبط الكود وفقًا لمتطلباتك المحددة، بما في ذلك مسار ملف المستند والتخصيص الإضافي

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية حل التعليقات والردود عليها في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن إدارة دقة التعليقات وتحديث حالة التعليقات وردودها وفقًا لمتطلباتك.

يساعد حل التعليقات في تتبع التعليقات وإدارتها داخل المستند. قم بتجربة حالات التعليقات المختلفة وقم بتخصيصها لتحسين عمليات التعاون والمراجعة في مستنداتك.

### الأسئلة الشائعة

#### س: كيف يمكنني حل تعليق في Aspose.Words لـ .NET؟

 ج: لحل تعليق في Aspose.Words لـ .NET، يمكنك استخدام`Comment.Resolve` طريقة تحديد`Comment` الكائن الذي تريد حله. سيؤدي هذا إلى وضع علامة على التعليق على أنه تم حله وإخفائه في المستند النهائي.

#### س: كيف يمكنني إضافة رد على تعليق تم حله في Aspose.Words لـ .NET؟

 ج: على الرغم من أن التعليقات التي تم حلها تكون مخفية بشكل افتراضي في المستند النهائي، إلا أنه لا يزال بإمكانك إضافة رد على تعليق تم حله باستخدام`Comment.AddReply` طريقة تحديد نص الرد والمكان الذي تريد إضافته.

#### س: كيف يمكنني عرض التعليقات التي تم حلها في Aspose.Words لـ .NET؟

 ج: بشكل افتراضي، يتم إخفاء التعليقات التي تم حلها في المستند النهائي. ومع ذلك، يمكنك إظهارها باستخدام`CommentOptions.ShowResolvedComments` ملكية`Document` الكائن وتعيينه على`true`.

#### س: كيف يمكنني إخفاء كافة التعليقات، بما في ذلك الردود، في Aspose.Words for .NET؟

 ج: لإخفاء كافة التعليقات، بما في ذلك الردود، في Aspose.Words for .NET، يمكنك استخدام`CommentOptions.CommentDisplayMode` ملكية`Document` الكائن وتعيينه على`CommentDisplayMode.None`.

#### س: هل يمكنني تحرير نص التعليق الذي تم حله في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك تحرير نص التعليق الذي تم حله في Aspose.Words for .NET عن طريق الوصول إلى`Comment.Text` خاصية المقابلة`Comment` الكائن وتعديل النص حسب الحاجة.