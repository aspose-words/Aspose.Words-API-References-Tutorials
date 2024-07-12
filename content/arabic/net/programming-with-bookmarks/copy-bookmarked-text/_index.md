---
title: انسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
linktitle: انسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: انسخ النص الذي تم وضع إشارة مرجعية عليه بسهولة بين مستندات Word باستخدام Aspose.Words لـ .NET. تعرف على كيفية القيام بذلك باستخدام هذا الدليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/copy-bookmarked-text/
---
## مقدمة

هل وجدت نفسك بحاجة إلى نسخ أقسام معينة من مستند Word إلى آخر؟ حسنًا، أنت محظوظ! سنرشدك في هذا البرنامج التعليمي إلى كيفية نسخ نص ذي إشارة مرجعية من مستند Word إلى آخر باستخدام Aspose.Words for .NET. سواء كنت تقوم بإنشاء تقرير ديناميكي أو إنشاء المستندات تلقائيًا، فسيعمل هذا الدليل على تبسيط العملية بالنسبة لك.

## المتطلبات الأساسية

قبل أن نتعمق، تأكد من أن لديك ما يلي:

-  Aspose.Words لمكتبة .NET: يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: Visual Studio أو أي بيئة تطوير .NET أخرى.
- المعرفة الأساسية بـ C#: الإلمام ببرمجة C# وإطار عمل .NET.

## استيراد مساحات الأسماء

للبدء، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## الخطوة 1: قم بتحميل المستند المصدر

أول الأشياء أولاً، تحتاج إلى تحميل المستند المصدر الذي يحتوي على النص الذي تم وضع إشارة مرجعية عليه والذي تريد نسخه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 هنا،`dataDir` هو المسار إلى دليل المستندات الخاص بك، و`Bookmarks.docx` هي الوثيقة المصدر.

## الخطوة 2: تحديد الإشارة المرجعية

بعد ذلك، حدد الإشارة المرجعية التي ترغب في نسخها من المستند المصدر.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 يستبدل`"MyBookmark1"` بالاسم الفعلي للإشارة المرجعية الخاصة بك.

## الخطوة 3: إنشاء مستند الوجهة

الآن، قم بإنشاء مستند جديد حيث سيتم نسخ النص الذي تم وضع إشارة مرجعية عليه.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## الخطوة 4: استيراد المحتوى الذي تم وضع إشارة مرجعية عليه

 لضمان الحفاظ على الأنماط والتنسيقات، استخدم`NodeImporter` لاستيراد المحتوى ذي الإشارة المرجعية من المستند المصدر إلى المستند الوجهة.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## الخطوة 5: تحديد أسلوب AppendBookmarkedText

هنا يحدث السحر. حدد طريقة للتعامل مع نسخ النص الذي تم وضع إشارة مرجعية عليه:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## الخطوة 6: احفظ مستند الوجهة

وأخيرًا، احفظ المستند الوجهة للتحقق من المحتوى المنسوخ.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## خاتمة

وهذا كل شيء! لقد نجحت في نسخ نص ذي إشارة مرجعية من مستند Word إلى آخر باستخدام Aspose.Words for .NET. تعتبر هذه الطريقة فعالة لأتمتة مهام معالجة المستندات، مما يجعل سير عملك أكثر كفاءة وانسيابية.

## الأسئلة الشائعة

### هل يمكنني نسخ إشارات مرجعية متعددة في وقت واحد؟
نعم، يمكنك التكرار عبر إشارات مرجعية متعددة واستخدام نفس الطريقة لنسخ كل واحدة منها.

### ماذا يحدث إذا لم يتم العثور على الإشارة المرجعية؟
 ال`Range.Bookmarks` سوف تعود الممتلكات`null`لذا تأكد من التعامل مع هذه الحالة لتجنب الاستثناءات.

### هل يمكنني الحفاظ على تنسيق الإشارة المرجعية الأصلية؟
 قطعاً! استخدام`ImportFormatMode.KeepSourceFormatting` يضمن الحفاظ على التنسيق الأصلي.

### هل هناك حد لحجم النص الذي تم وضع إشارة مرجعية عليه؟
لا يوجد حد محدد، ولكن قد يختلف الأداء مع المستندات الكبيرة للغاية.

### هل يمكنني نسخ النص بين تنسيقات مستندات Word المختلفة؟
نعم، يدعم Aspose.Words تنسيقات Word المختلفة، وتعمل الطريقة عبر هذه التنسيقات.