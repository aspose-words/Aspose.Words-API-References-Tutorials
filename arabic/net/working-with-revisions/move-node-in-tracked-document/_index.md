---
title: نقل العقدة في المستند المتعقب
linktitle: نقل العقدة في المستند المتعقب
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: انقل العقد في مستند تم تعقبه باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/move-node-in-tracked-document/
---

في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية تحريك عقدة في مستند Word متعقب باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة الأولى: إنشاء المستند

الخطوة الأولى هي إنشاء مستند جديد وإضافة فقرات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## الخطوة 2: تتبع المراجعات

سنقوم بتمكين تتبع المراجعة في المستند.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## الخطوة 3: انقل العقدة

سننقل عقدة (فقرة) من موضع إلى آخر أثناء إنشاء المراجعات.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## الخطوة الرابعة: التوقف عن تتبع التعليقات

سنتوقف عن تتبع المراجعات في المستند.

```csharp
doc.StopTrackRevisions();
```

## الخطوة 5: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### مثال على شفرة المصدر لـ Move Node In Tracked Document باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لنقل عقدة في مستند متتبع باستخدام Aspose.Words for .NET:


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// بدء تتبع المراجعات.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// إنشاء مراجعات عند نقل عقدة من موقع إلى آخر.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// أوقف عملية تتبع المراجعات.
doc.StopTrackRevisions();

// هناك 3 فقرات إضافية في نطاق الانتقال من.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية نقل عقدة في مستند Word متعقب باستخدام Aspose.Words for .NET. باتباع خطوات إنشاء المستند ، وتمكين تتبع المراجعة ، وتحريك العقدة ، وإيقاف تتبع المراجعة ، تمكنا من إجراء هذه المعالجة بنجاح. Aspose.Words for .NET أداة قوية لمعالجة الكلمات مع مستندات Word وتوفر ميزات متقدمة لإدارة المراجعات. يمكنك الآن استخدام هذه المعرفة لنقل العقد في مستندات Word الخاصة بك أثناء تتبع المراجعات باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكنني تمكين تتبع المراجعة في مستند Aspose.Words for .NET؟

ج: لتمكين تتبع المراجعة في مستند Aspose.Words for .NET ، يمكنك استخدام`StartTrackRevisions` طريقة`Document` هدف. تأخذ هذه الطريقة كمعلمات اسم مؤلف المراجعات وتاريخ بدء متابعة المراجعات.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### س: كيف يمكنني نقل عقدة في مستند متعقب بدون إنشاء مراجعات؟

 ج: إذا كنت تريد نقل عقدة في مستند متتبع دون إنشاء مراجعات ، فيمكنك استخدام ملف`Remove` و`InsertAfter` أو`InsertBefore` طرق`Node` هدف. على سبيل المثال ، لنقل فقرة بعد فقرة أخرى ، يمكنك استخدام الكود التالي:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### س: كيف يمكنني إيقاف تتبع المراجعة في مستند Aspose.Words for .NET؟

 ج: لإيقاف تتبع المراجعات في مستند Aspose.Words for .NET ، يمكنك استخدام`StopTrackRevisions` طريقة`Document` هدف.

```csharp
doc.StopTrackRevisions();
```