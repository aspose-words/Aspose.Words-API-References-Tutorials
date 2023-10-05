---
title: قبول المراجعات
linktitle: قبول المراجعات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية قبول المراجعات على مستند Word باستخدام Aspose.Words لـ .NET
type: docs
weight: 10
url: /ar/net/working-with-revisions/accept-revisions/
---

في هذا البرنامج التعليمي، سنرشدك خلال قبول المراجعات على مستند Word باستخدام ميزة قبول المراجعات في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وقبول التغييرات على المستند.

## الخطوة 1: إضافة محتوى المستند وتحريره

في هذا المثال، نقوم بإنشاء مستند وإضافة محتوى. نستخدم عدة فقرات لتوضيح التغييرات والمراجعات. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// أضف نصًا إلى الفقرة الأولى، ثم أضف فقرتين أخريين.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## الخطوة 2: تتبع المراجعات وإضافة المراجعات

نقوم بتمكين تتبع المراجعة وإضافة مراجعة إلى المستند. إليك الطريقة:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// هذه الفقرة عبارة عن مراجعة وستحتوي على مجموعة العلامات "IsInsertRevision" المقابلة.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## الخطوة 3: حذف فقرة وإدارة المراجعات

نقوم بحذف فقرة والتحقق من المراجعات المحفوظة. إليك الطريقة:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// بينما نقوم بتتبع المراجعات، فإن الفقرة لا تزال موجودة في المستند، وستحتوي على مجموعة العلامة "IsDeleteRevision"
// وسيتم عرضها كمراجعة في برنامج Microsoft Word، حتى نقبل جميع المراجعات أو نرفضها.
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

## الخطوة 5: التوقف عن تتبع المراجعات

سنقوم بإيقاف تتبع المراجعات حتى لا تظهر التغييرات التي يتم إجراؤها على المستند كمراجعات بعد الآن. إليك الطريقة:

```csharp
doc.StopTrackRevisions();
```
## الخطوة 6: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### مثال على التعليمات البرمجية المصدر لقبول المراجعات باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لقبول التغييرات في مستند باستخدام Aspose.Words for .NET:


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// أضف نصًا إلى الفقرة الأولى، ثم أضف فقرتين أخريين.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//لدينا ثلاث فقرات، لم يتم تسجيل أي منها على أنها أي نوع من المراجعة
// إذا قمنا بإضافة/إزالة أي محتوى في المستند أثناء تتبع المراجعات،
// سيتم عرضها على هذا النحو في المستند ويمكن قبولها/رفضها.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// هذه الفقرة عبارة عن مراجعة وستحتوي على مجموعة العلامات "IsInsertRevision" وفقًا لذلك.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// احصل على مجموعة فقرات المستند وقم بإزالة فقرة.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// نظرًا لأننا نقوم بتتبع المراجعات، فإن الفقرة لا تزال موجودة في المستند، وستحتوي على مجموعة "IsDeleteRevision"
// وسيتم عرضه كمراجعة في برنامج Microsoft Word، حتى نقبل جميع المراجعات أو نرفضها.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// تتم إزالة فقرة حذف المراجعة بمجرد قبول التغييرات.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// يؤدي إيقاف تتبع المراجعات إلى ظهور هذا النص كنص عادي.
// لا يتم احتساب المراجعات عند تغيير المستند.
doc.StopTrackRevisions();

// احفظ المستند.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية قبول المراجعات في مستند Word باستخدام ميزة قبول المراجعات في Aspose.Words for .NET. لقد اتبعنا خطوات إضافة محتوى المستند وتحريره، وتتبع المراجعات، وحذف فقرة تمت مراجعتها، وقبول كافة التغييرات، وإيقاف تعقب المراجعات. يمكنك الآن تطبيق هذه المعرفة لإدارة المراجعات بشكل فعال في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني تمكين تتبع المراجعة في Aspose.Words لـ .NET؟

#### الحل 1:

 ج: لتمكين تعقب المراجعة في Aspose.Words لـ .NET، استخدم`StartTrackRevisions` طريقة`Document` الكائن وحدد اسم المؤلف وتاريخ البدء لتتبع المراجعة.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### الحل 2:

 ج: يمكنك أيضًا تمكين تتبع المراجعة باستخدام`Document` المنشئ الذي يقبل`trackRevisions` و`author` حدود.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### س: كيف يتم قبول كافة التغييرات في مستند باستخدام Aspose.Words لـ .NET؟

 ج: استخدم`AcceptAllRevisions` طريقة`Document` كائن لقبول كافة التغييرات التي تم إجراؤها على المستند.

```csharp
doc.AcceptAllRevisions();
```

#### س: كيف يمكنني حفظ مستند معدل بالمراجعات المقبولة؟

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند المعدل مع المراجعات المقبولة. تأكد من توفير مسار الملف الصحيح.

```csharp
doc.Save("path/to/the/document.docx");
```

#### س: كيف يمكنني إيقاف تتبع المراجعات في Aspose.Words لـ .NET؟

 ج: استخدم`StopTrackRevisions` طريقة`Document` كائن لإيقاف مراجعات التتبع.

```csharp
doc.StopTrackRevisions();
```

#### س: كيف يمكنني حذف فقرة تمت مراجعتها في مستند باستخدام Aspose.Words for .NET؟

 ج: لإزالة فقرة تمت مراجعتها في مستند، يمكنك استخدام الخيار`Remove` طريقة جمع الفقرات.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```