---
title: قبول المراجعات
linktitle: قبول المراجعات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية قبول المراجعات على مستند Word باستخدام Aspose.Words for .NET
type: docs
weight: 10
url: /it/net/working-with-revisions/accept-revisions/
---

في هذا البرنامج التعليمي ، سنرشدك خلال قبول المراجعات على مستند Word باستخدام ميزة قبول التنقيحات في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر وقبول التغييرات على المستند.

## الخطوة 1: إضافة وتحرير محتوى المستند

في هذا المثال ، نقوم بإنشاء مستند وإضافة محتوى. نستخدم عدة فقرات لتوضيح التغييرات والمراجعات. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// أضف نصًا إلى الفقرة الأولى ، ثم أضف فقرتين أخريين.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## الخطوة 2: تتبع المراجعات وإضافة التعليقات

نقوم بتمكين تتبع المراجعة وإضافة مراجعة إلى المستند. إليك الطريقة:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//هذه الفقرة هي مراجعة وسيكون لها مجموعة إشارة "IsInsertRevision" المطابقة.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## الخطوة 3: حذف فقرة وإدارة المراجعات

نحذف فقرة ونبحث عن المراجعات المحفوظة. إليك الطريقة:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// نظرًا لأننا نتتبع المراجعات ، لا تزال الفقرة موجودة في المستند ، وستحتوي على مجموعة علامة "IsDeleteRevision"
// وسيتم عرضها كمراجعة في Microsoft Word ، حتى نقبل أو نرفض جميع المراجعات.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## الخطوة 4: قبول التغييرات

نحن نقبل جميع التغييرات على الوثيقة. إليك الطريقة:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## الخطوة الخامسة: التوقف عن تتبع المراجعات

سنقوم بإيقاف تعقب المراجعات حتى لا تظهر التغييرات التي تم إجراؤها على المستند كمراجعات. إليك الطريقة:

```csharp
doc.StopTrackRevisions();
```
## الخطوة 6: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### مثال على شفرة المصدر لقبول المراجعات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لقبول التغييرات في مستند باستخدام Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Body body = doc.FirstSection.Body;
	Paragraph para = body.FirstParagraph;

	// أضف نصًا إلى الفقرة الأولى ، ثم أضف فقرتين أخريين.
	para.AppendChild(new Run(doc, "Paragraph 1. "));
	body.AppendParagraph("Paragraph 2. ");
	body.AppendParagraph("Paragraph 3. ");

	// لدينا ثلاث فقرات ، لم يتم تسجيل أي منها كأي نوع من المراجعة
	//إذا أضفنا / أزلنا أي محتوى في المستند أثناء تتبع المراجعات ،
	// سيتم عرضها على هذا النحو في المستند ويمكن قبولها / رفضها.
	doc.StartTrackRevisions("John Doe", DateTime.Now);

	// هذه الفقرة هي مراجعة وستحتوي على مجموعة الرايات "IsInsertRevision".
	para = body.AppendParagraph("Paragraph 4. ");
	Assert.True(para.IsInsertRevision);

	// احصل على مجموعة فقرات المستند وقم بإزالة فقرة.
	ParagraphCollection paragraphs = body.Paragraphs;
	Assert.AreEqual(4, paragraphs.Count);
	para = paragraphs[2];
	para.Remove();

	// نظرًا لأننا نتتبع المراجعات ، فلا تزال الفقرة موجودة في المستند ، وستحتوي على مجموعة "IsDeleteRevision"
	// وسيتم عرضها كمراجعة في Microsoft Word ، حتى نقبل أو نرفض جميع المراجعات.
	Assert.AreEqual(4, paragraphs.Count);
	Assert.True(para.IsDeleteRevision);

	// تتم إزالة فقرة مراجعة الحذف بمجرد قبول التغييرات.
	doc.AcceptAllRevisions();
	Assert.AreEqual(3, paragraphs.Count);
	Assert.That(para, Is.Empty);

	// يؤدي إيقاف تتبع المراجعات إلى ظهور هذا النص كنص عادي.
	// لا يتم احتساب المراجعات عند تغيير المستند.
	doc.StopTrackRevisions();

	// احفظ المستند.
	doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
            
```
