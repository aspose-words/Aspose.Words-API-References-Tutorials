---
title: نقل العقدة في المستند المتعقب
linktitle: نقل العقدة في المستند المتعقب
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية نقل العقد في مستند Word المتعقب باستخدام Aspose.Words لـ .NET من خلال دليلنا التفصيلي خطوة بخطوة. مثالية للمطورين.
type: docs
weight: 10
url: /ar/net/working-with-revisions/move-node-in-tracked-document/
---
## مقدمة

مرحبًا، عشاق Aspose.Words! إذا كنت في حاجة إلى نقل عقدة في مستند Word أثناء تعقب المراجعات، فأنت في المكان الصحيح. واليوم، سنتعمق في كيفية تحقيق ذلك باستخدام Aspose.Words for .NET. لن تتعلم العملية خطوة بخطوة فحسب، بل ستلتقط أيضًا بعض النصائح والحيل لجعل معالجة المستندات الخاصة بك سلسة وفعالة.

## المتطلبات الأساسية

قبل أن نبدأ ببعض التعليمات البرمجية، دعونا نتأكد من حصولك على كل ما تحتاجه:

-  Aspose.Words لـ .NET: قم بتنزيله[هنا](https://releases.aspose.com/words/net/).
- بيئة .NET: تأكد من إعداد بيئة تطوير .NET متوافقة.
- المعرفة الأساسية لـ C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لـ C#.

حصلت على كل شيء؟ عظيم! دعنا ننتقل إلى مساحات الأسماء التي نحتاج إلى استيرادها.

## استيراد مساحات الأسماء

أول الأشياء أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية. تعتبر هذه العناصر ضرورية للعمل مع Aspose.Words والتعامل مع عقد المستندات.

```csharp
using Aspose.Words;
using System;
```

حسنًا، دعنا نقسم العملية إلى خطوات يمكن التحكم فيها. سيتم شرح كل خطوة بالتفصيل لضمان فهمك لما يحدث في كل نقطة.

## الخطوة 1: تهيئة المستند

 للبدء، نحتاج إلى تهيئة مستند جديد واستخدام ملف`DocumentBuilder` لإضافة بعض الفقرات.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// - اضافة بعض الفقرات
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// تحقق من عدد الفقرات الأولي
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## الخطوة 2: ابدأ بتتبع المراجعات

بعد ذلك، نحتاج إلى البدء في تتبع المراجعات. يعد هذا أمرًا بالغ الأهمية لأنه يسمح لنا برؤية التغييرات التي تم إجراؤها على المستند.

```csharp
// ابدأ بتتبع المراجعات
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## الخطوة 3: نقل العقد

الآن يأتي الجزء الأساسي من مهمتنا: نقل العقدة من موقع إلى آخر. سنقوم بنقل الفقرة الثالثة ووضعها قبل الفقرة الأولى.

```csharp
// تحديد العقدة المراد نقلها ونطاقها النهائي
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// نقل العقد ضمن النطاق المحدد
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## الخطوة 4: إيقاف تتبع المراجعات

بمجرد قيامنا بنقل العقد، نحتاج إلى التوقف عن تتبع المراجعات.

```csharp
// إيقاف تتبع المراجعات
doc.StopTrackRevisions();
```

## الخطوة 5: احفظ المستند

أخيرًا، دعونا نحفظ مستندنا المعدل في الدليل المحدد.

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// إخراج عدد الفقرات النهائي
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## خاتمة

وهنا لديك! لقد نجحت في نقل عقدة في مستند تم تعقبه باستخدام Aspose.Words لـ .NET. تسهل هذه المكتبة القوية التعامل مع مستندات Word برمجياً. سواء كنت تقوم بإنشاء التغييرات أو تحريرها أو تتبعها، فإن Aspose.Words ستوفر لك كل ما تحتاجه. لذا، تفضل وجربها. ترميز سعيد!

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟

Aspose.Words for .NET هي مكتبة فئة للعمل مع مستندات Word برمجيًا. فهو يسمح للمطورين بإنشاء مستندات Word وتحريرها وتحويلها وطباعتها ضمن تطبيقات .NET.

### كيف يمكنني تتبع المراجعات في مستند Word باستخدام Aspose.Words؟

 لتتبع المراجعات، استخدم`StartTrackRevisions` الطريقة على`Document` هدف. سيؤدي هذا إلى تمكين تتبع المراجعة، وإظهار أي تغييرات تم إجراؤها على المستند.

### هل يمكنني نقل عقد متعددة في Aspose.Words؟

نعم، يمكنك نقل عقد متعددة عن طريق التكرار عليها واستخدام أساليب مثل`InsertBefore` أو`InsertAfter` لوضعهم في المكان المطلوب.

### كيف يمكنني إيقاف تتبع المراجعات في Aspose.Words؟

 استخدم`StopTrackRevisions` الطريقة على`Document` كائن لإيقاف تتبع المراجعات.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Words لـ .NET؟

 يمكنك العثور على وثائق مفصلة[هنا](https://reference.aspose.com/words/net/).