---
title: تجاهل النص داخل حذف المراجعات
linktitle: تجاهل النص داخل حذف المراجعات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في مكتبة Aspose.Words for .NET. هذه الميزة مفيدة عندما نريد تجاهل النص داخل مراجعات الحذف عند معالجة الكلمات مع المستندات.

## نظرة عامة على Aspose.Words لمكتبة .NET

قبل التعمق في تفاصيل التعليمات البرمجية، اسمحوا لي أن أقدم بإيجاز مكتبة Aspose.Words for .NET. إنها مكتبة قوية تسمح بإنشاء وتعديل وتحويل مستندات Word في تطبيقات .NET. ويقدم العديد من الميزات المتقدمة لمعالجة الكلمات مع المستندات، بما في ذلك إدارة المراجعة.

## فهم ميزة "تجاهل النص داخل حذف المراجعات".

تتيح لك ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words for .NET تحديد ما إذا كان يجب تجاهل النص الموجود داخل مراجعات الحذف أثناء عمليات معينة، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة، لا يتم أخذ النص المحذوف داخل المراجعات في الاعتبار أثناء العمليات.

## الخطوة 1: إنشاء مستند جديد باستخدام Aspose.Words لـ .NET

 قبل أن نبدأ في معالجة النص في المستند، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: إدراج نص غير منقح في المستند

 بمجرد حصولنا على مستند، يمكننا إدراج نص لم تتم مراجعته باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج النص "نص محذوف"، يمكننا استخدام الأمر`Writeln` و`Write` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## الخطوة 3: إزالة فقرة مع مراجعات التتبع

لتوضيح استخدام ميزة "تجاهل النص داخل حذف المراجعات"، سنقوم بحذف فقرة من المستند باستخدام تتبع المراجعة. سيسمح لنا هذا بمعرفة كيف تؤثر هذه الميزة على العمليات اللاحقة.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## الخطوة 4: تطبيق ميزة "تجاهل النص داخل حذف المراجعات".

 الآن بعد أن قمنا بإعداد وثيقتنا عن طريق حذف فقرة، يمكننا تمكين ميزة "تجاهل النص داخل حذف المراجعات" باستخدام`FindReplaceOptions` هدف. سوف نقوم بتعيين`IgnoreDeleted`الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## الخطوة 5: استخدام التعبيرات العادية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص المستند، سوف نستخدم التعبيرات العادية. في مثالنا، سوف نقوم بالبحث عن كافة تواجدات الحرف "e" واستبدالها بعلامة النجمة "* ". .شبكة`Regex` يتم استخدام الطبقة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 6: عرض مخرجات الوثيقة المعدلة

 بعد تطبيق البحث والاستبدال، يمكننا عرض محتوى المستند الذي تم تغييره باستخدام ملف`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 7: تعديل الخيارات لتضمين النص المحذوف

 إذا أردنا تضمين النص المحذوف في نتيجة الإخراج، فيمكننا تغيير الخيارات لعدم تجاهل النص المحذوف. لهذا سوف نقوم بتعيين`IgnoreDeleted`الملكية ل`false`:

```csharp
options. IgnoreDeleted = false;
```

## الخطوة 8: إخراج المستند المعدل بالنص المحذوف

بعد تغيير الخيارات يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع تضمين النص المحذوف:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### مثال على التعليمات البرمجية المصدر لتجاهل النص داخل وحذف المراجعات باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام ميزة "تجاهل النص داخل حذف المراجعات" مع Aspose.Words لـ .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// أدخل نصًا غير منقح.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// قم بإزالة الفقرة الأولى مع مراجعات التتبع.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words لـ .NET. هذه الميزة مفيدة لتجاهل النص الموجود داخل مراجعات الحذف عند معالجة المستندات. لقد اتبعنا دليلًا خطوة بخطوة لإنشاء مستند، وإدراج نص، وحذف فقرة مع تتبع المراجعة، وتطبيق ميزة "تجاهل النص داخل حذف المراجعات"، وإجراء عمليات البحث والاستبدال.

### الأسئلة الشائعة

#### س: ما هي وظيفة "تجاهل النص داخل حذف المراجعات" في Aspose.Words لـ .NET؟

ج: تتيح لك وظيفة "تجاهل النص داخل حذف المراجعات" في Aspose.Words لـ .NET تحديد ما إذا كان يجب تجاهل النص الموجود داخل مراجعات الحذف أثناء عمليات معينة، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة، لا يتم أخذ النص المحذوف داخل المراجعات في الاعتبار أثناء العمليات.

#### س: ما هو Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET هي مكتبة قوية لإنشاء وتحرير وتحويل مستندات Word إلى تطبيقات .NET. ويقدم العديد من الميزات المتقدمة لمعالجة الكلمات مع المستندات، بما في ذلك إدارة المراجعة.

#### س: كيفية إنشاء مستند جديد في Aspose.Words لـ .NET؟

 ج: قبل أن تبدأ في معالجة النص في مستند، تحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف. فيما يلي نموذج التعليمات البرمجية لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```

#### س: كيفية إدراج نص غير محرر في مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج نص لم تتم مراجعته باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج النص "نص محذوف"، يمكنك استخدام الأمر`Writeln` و`Write` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### س: كيف يمكنني حذف فقرة بها تتبع المراجعة في Aspose.Words لـ .NET؟

ج: لتوضيح استخدام وظيفة "تجاهل النص داخل حذف المراجعات"، سنقوم بحذف فقرة من المستند باستخدام تتبع المراجعة. سيسمح لنا هذا برؤية كيف تؤثر هذه الوظيفة على العمليات اللاحقة.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### س: كيفية تمكين ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words لـ .NET؟

 ج: الآن بعد أن قمنا بإعداد وثيقتنا عن طريق حذف فقرة، يمكننا تمكين ميزة "تجاهل النص داخل حذف المراجعات" باستخدام`FindReplaceOptions` هدف. سوف نقوم بتعيين`IgnoreDeleted`الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### س: كيف يتم البحث والاستبدال باستخدام التعبيرات العادية في Aspose.Words لـ .NET؟

ج: لإجراء عمليات البحث والاستبدال على نص المستند، سوف نستخدم التعبيرات العادية. في مثالنا، سوف نقوم بالبحث عن كافة تواجدات الحرف "e" واستبدالها بعلامة النجمة "* ". سوف نستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### س: كيف يمكن عرض محتوى المستند الذي تم تغييره في Aspose.Words لـ .NET؟

ج: بعد تطبيق البحث والاستبدال، يمكننا عرض محتوى المستند الذي تم تغييره باستخدام ملف`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

#### س: كيف يتم تضمين النص المحذوف في نتيجة الإخراج في Aspose.Words لـ .NET؟

 ج: إذا أردنا تضمين النص المحذوف في نتيجة الإخراج، فيمكننا تغيير الخيارات لعدم تجاهل النص المحذوف. لهذا، سوف نقوم بتعيين`IgnoreDeleted`الملكية ل`false`:

```csharp
options. IgnoreDeleted = false;
```

#### س: كيف يتم إظهار المستند الذي تم تحريره مع النص المحذوف في Aspose.Words لـ .NET؟

ج: بعد تغيير الخيارات يمكننا إجراء بحث جديد واستبدال للحصول على النتيجة مع تضمين النص المحذوف:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
