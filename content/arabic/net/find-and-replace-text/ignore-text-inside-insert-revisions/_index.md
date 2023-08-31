---
title: تجاهل النص داخل إدراج المراجعات
linktitle: تجاهل النص داخل إدراج المراجعات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام ميزة "تجاهل النص داخل إدراج المراجعات" في Aspose.Words لـ .NET لمعالجة مراجعات الإدراج في مستندات Word.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة Ignore Text Inside Insert Revisions في مكتبة Aspose.Words for .NET. تكون هذه الميزة مفيدة عندما نريد تجاهل النص الموجود داخل مراجعات الإدراج أثناء معالجة المستندات.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في معالجة النص داخل مراجعات الإدراج، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: إدراج نص مع تتبع المراجعة

 بمجرد حصولنا على مستند، يمكننا إدراج نص مع تتبع المراجعة باستخدام ملف`DocumentBuilder`هدف. على سبيل المثال، لإدراج النص "المدرج" مع تتبع المراجعة، يمكننا استخدام الأمر`StartTrackRevisions`, `Writeln` و`StopTrackRevisions` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## الخطوة 3: أدخل نصًا لم تتم مراجعته

 بالإضافة إلى النص الذي يتضمن تتبع المراجعة، يمكننا أيضًا إدراج نص غير منقح باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج النص "نص" بدون مراجعة، يمكننا استخدام الأمر`Write` طريقة:

```csharp
builder.Write("Text");
```

## الخطوة 4: استخدام وظيفة تجاهل النص داخل إدراج المراجعات

 لتجاهل النص الموجود داخل إدراج المراجعات في العمليات اللاحقة، يمكننا استخدام أ`FindReplaceOptions` الكائن وتعيين`IgnoreInserted` الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## الخطوة 5: استخدام التعبيرات العادية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص الوثيقة، سوف نستخدم التعبيرات العادية. في مثالنا، سوف نقوم بالبحث عن كافة تواجدات الحرف "e" واستبدالها بعلامة النجمة "* ". سوف نستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 6: عرض مخرجات المستند المعدل

بعد تطبيق البحث والاستبدال، يمكننا عرض محتوى المستند الذي تم تغييره باستخدام ملف`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 7: تغيير الخيارات لتضمين إدراج المراجعات

إذا أردنا تضمين النص الموجود داخل مراجعات الإدراج في نتيجة الإخراج، فيمكننا تغيير الخيارات حتى لا نتجاهل مراجعات الإدراج. لهذا سوف نقوم بتعيين`IgnoreInserted` الملكية ل`false`:

```csharp
options.IgnoreInserted = false;
```

## الخطوة 8: عرض المستند المعدل مع إدراج المراجعات

بعد تغيير الخيارات يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع النص الموجود داخل إدراج المراجعات المتضمنة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### مثال على التعليمات البرمجية المصدر لتجاهل النص داخل إدراج المراجعات باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام وظيفة Ignore Text Inside Insert Revisions مع Aspose.Words for .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// إدراج نص مع مراجعات التتبع.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// أدخل نصًا غير منقح.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة Ignore Text Inside Insert Revisions في Aspose.Words for .NET. لقد اتبعنا دليلًا خطوة بخطوة لإنشاء مستند، وإدراج نص مع تتبع المراجعات والنص غير المنقح، باستخدام وظيفة تجاهل النص داخل إدراج المراجعات، وإجراء عمليات البحث والاستبدال بالتعبيرات العادية، وعرض المستند المعدل.

### الأسئلة الشائعة

#### س: ما هي ميزة "تجاهل النص داخل إدراج المراجعات" في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة "تجاهل النص داخل مراجعات الإدراج" في Aspose.Words لـ .NET تحديد ما إذا كان يجب تجاهل النص الموجود داخل مراجعات الإدراج أثناء عمليات معينة، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة، لا يتم أخذ النص الموجود داخل مراجعات الإدراج في الاعتبار أثناء العمليات.

#### س: كيف يمكنني إنشاء مستند جديد باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء مستند جديد باستخدام Aspose.Words لـ .NET، يمكنك إنشاء مثيل`Document` هدف. فيما يلي مثال على كود C# لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```

#### س: كيف يمكنني إدراج نص مع تتبع المراجعة في Aspose.Words لـ .NET؟

ج: بمجرد حصولك على مستند، يمكنك إدراج نص مع تتبع المراجعة باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج النص "المدرج" مع تتبع المراجعة، يمكنك استخدام الملف`StartTrackRevisions`, `Writeln` ، و`StopTrackRevisions` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### س: كيف يمكنني إدراج نص غير منقح في Aspose.Words لـ .NET؟

 ج: بالإضافة إلى النص الذي يتضمن تتبع المراجعة، يمكنك أيضًا إدراج نص غير منقح باستخدام`DocumentBuilder` هدف. على سبيل المثال، لإدراج النص "نص" بدون مراجعة، يمكنك استخدام الأمر`Write` طريقة:

```csharp
builder.Write("Text");
```

#### س: كيف يمكنني تجاهل النص الموجود داخل إدراج المراجعات في Aspose.Words لـ .NET؟

 ج: لتجاهل النص الموجود داخل إدراج المراجعات أثناء العمليات اللاحقة، يمكنك استخدام ملف`FindReplaceOptions` الكائن وتعيين`IgnoreInserted` الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### س: كيف يمكنني إجراء البحث والاستبدال باستخدام التعبيرات العادية في Aspose.Words لـ .NET؟

 ج: لإجراء عمليات البحث والاستبدال على نص المستند باستخدام التعبيرات العادية، يمكنك استخدام .NET`Regex` فصل. على سبيل المثال، للبحث عن كافة تواجدات الحرف "e" واستبدالها بعلامة النجمة "* "، يمكنك إنشاء`Regex` الكائن واستخدامه مع`Replace` طريقة:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### س: كيف يمكنني عرض المخرجات المعدلة للمستند في Aspose.Words لـ .NET؟

 ج: بعد تطبيق عمليات البحث والاستبدال، يمكنك عرض المحتوى الذي تم تغييره للمستند باستخدام الزر`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

#### س: كيف يمكنني تضمين مراجعات الإدراج في نتيجة الإخراج في Aspose.Words for .NET؟

 ج: لتضمين النص الموجود داخل مراجعات الإدراج في نتيجة الإخراج، يمكنك تغيير الخيارات حتى لا تتجاهل مراجعات الإدراج. لهذا يمكنك ضبط`IgnoreInserted` ملكية`FindReplaceOptions` يعترض على`false`:

```csharp
options.IgnoreInserted = false;
```

#### س: كيف يمكنني عرض المستند المعدل مع مراجعات الإدراج في Aspose.Words لـ .NET؟

ج: بعد تغيير الخيارات لتضمين مراجعات الإدراج، يمكنك إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع تضمين النص الموجود داخل مراجعات الإدراج:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```