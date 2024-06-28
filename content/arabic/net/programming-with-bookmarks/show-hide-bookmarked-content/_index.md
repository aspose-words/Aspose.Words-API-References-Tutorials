---
title: إظهار إخفاء المحتوى ذي الإشارة المرجعية في مستند Word
linktitle: إظهار إخفاء المحتوى ذي الإشارة المرجعية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إظهار المحتوى ذي الإشارة المرجعية أو إخفائه ديناميكيًا في مستندات Word باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## مقدمة

مرحبًا يا من هناك! هل سبق لك أن أردت التحكم في رؤية محتوى معين داخل مستند Word بناءً على شروط معينة؟ باستخدام Aspose.Words for .NET، يمكنك إظهار المحتوى ذي الإشارة المرجعية أو إخفائه ديناميكيًا باستخدام بضعة أسطر فقط من التعليمات البرمجية. في هذا البرنامج التعليمي، سأرشدك خلال العملية خطوة بخطوة، مع التأكد من فهمك لكل جزء من التعليمات البرمجية. في النهاية، ستكون محترفًا في التعامل مع الإشارات المرجعية في مستندات Word. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، دعونا نتأكد من أن لديك كل ما تحتاجه:

1. المعرفة الأساسية بـ C#: يجب أن تكون مرتاحًا لبناء جملة C# ومفاهيمها.
2.  Aspose.Words لـ .NET: قم بتنزيله[هنا](https://releases.aspose.com/words/net/) . إذا لم تكن مستعدًا للشراء، يمكنك البدء بـ[تجربة مجانية](https://releases.aspose.com/).
3. Visual Studio: أي إصدار حديث سوف يعمل، ولكن يوصى باستخدام الإصدار الأحدث.
4. .NET Framework: تأكد من تثبيته على جهازك.

على استعداد للبدء؟ عظيم! لنبدأ باستيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

لاستخدام Aspose.Words لـ .NET، نحتاج إلى استيراد مساحات الأسماء المطلوبة. تضمن هذه الخطوة أن نتمكن من الوصول إلى جميع الفئات والأساليب التي سنستخدمها.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

تعد مساحات الأسماء هذه ضرورية للعمل مع مستندات Word ومعالجة محتواها.

## الخطوة 1: إعداد الوثيقة

أولاً، لنقم بإنشاء مستند Word جديد ومنشئ المستندات. يساعدنا منشئ المستندات على إضافة المحتوى ومعالجته بسهولة داخل المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

في هذه الخطوة، نقوم بتهيئة مستند جديد ومنشئ المستندات. وهذا يهيئ بيئتنا لمزيد من العمليات.

## الخطوة 2: إضافة محتوى مرجعي

بعد ذلك، سنقوم بإضافة بعض المحتوى إلى المستند وإنشاء إشارة مرجعية حوله. ستساعدنا هذه الإشارة المرجعية في تحديد المحتوى ومعالجته.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 هنا، نضيف بعض النص قبل وبعد المحتوى الذي تم وضع إشارة مرجعية عليه. ال`StartBookmark` و`EndBookmark` تحدد الطرق حدود الإشارة المرجعية.

## الخطوة 3: إدراج حقل شرطي

للتحكم في رؤية المحتوى الذي تم وضع إشارة مرجعية عليه، سنستخدم حقلاً شرطيًا. سيتحقق هذا الحقل من الحالة ويعرض المحتوى أو يخفيه وفقًا لذلك.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

في هذه الخطوة، نقوم بإدراج حقل IF الذي يتحقق من قيمة الإشارة المرجعية. إذا كانت القيمة "صحيحة"، فسيتم عرض "مرئي"؛ وإلا فإنه سيتم عرض "مخفي".

## الخطوة 4: إعادة ترتيب العقد

بعد ذلك، نحتاج إلى إعادة ترتيب العقد لضمان تطبيق المنطق الشرطي بشكل صحيح على المحتوى الذي تم وضع إشارة مرجعية عليه.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

هنا، نقوم بتحريك العقد للتأكد من أن الشرط يشمل المحتوى الذي تم وضع إشارة مرجعية عليه بشكل صحيح.

## الخطوة 5: تنفيذ دمج المراسلات

وأخيرًا، سنقوم بتنفيذ عملية دمج البريد لتعيين قيمة الإشارة المرجعية وتحديد ما إذا كان يجب إظهار المحتوى أم إخفاؤه.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

تقوم هذه الخطوة بتعيين قيمة الإشارة المرجعية على "صحيح"، مما سيجعل المحتوى مرئيًا بناءً على حالتنا.

## الخطوة 6: حفظ المستند

بعد كل المعالجات، الخطوة الأخيرة هي حفظ المستند المعدل.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

وهنا نقوم بحفظ المستند باسم ملف وصفي للإشارة إلى التغييرات.

## خاتمة

 وهذا كل شيء! لقد تعلمت بنجاح كيفية إظهار أو إخفاء المحتوى الذي تم وضع إشارة مرجعية عليه في مستند Word باستخدام Aspose.Words for .NET. يغطي هذا البرنامج التعليمي إنشاء مستند، وإضافة الإشارات المرجعية، وإدراج الحقول الشرطية، وإعادة ترتيب العقد، وتنفيذ دمج البريد. يقدم Aspose.Words عددًا كبيرًا من الميزات، لذا لا تتردد في استكشافه[وثائق واجهة برمجة التطبيقات](https://reference.aspose.com/words/net/) لمزيد من القدرات المتقدمة.

## الأسئلة الشائعة

### 1. ما هو Aspose.Words لـ .NET؟

Aspose.Words for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات Word وتعديلها وتحويلها برمجيًا. يتم استخدامه على نطاق واسع لمهام أتمتة المستندات.

### 2. هل يمكنني استخدام Aspose.Words لـ .NET مجانًا؟

 يمكنك تجربة Aspose.Words لـ .NET باستخدام ملف[تجربة مجانية](https://releases.aspose.com/). للاستخدام طويل الأمد، ستحتاج إلى شراء ترخيص.

### 3. كيف يمكنني تعديل الخصائص الأخرى للإشارة المرجعية؟

 يسمح لك Aspose.Words بمعالجة الخصائص المختلفة للإشارة المرجعية، مثل النص والموقع. الرجوع إلى[وثائق واجهة برمجة التطبيقات](https://reference.aspose.com/words/net/) للحصول على تعليمات مفصلة.

### 4. كيف يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟

يمكنك الحصول على الدعم من خلال زيارة[Aspose منتدى الدعم](https://forum.aspose.com/c/words/8).

### 5. هل يمكنني التعامل مع أنواع أخرى من المحتوى باستخدام Aspose.Words لـ .NET؟

نعم، يدعم Aspose.Words for .NET أنواعًا مختلفة من معالجة المحتوى، بما في ذلك النصوص والصور والجداول والمزيد.