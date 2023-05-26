---
title: تجاهل النص داخل إدراج المراجعات
linktitle: تجاهل النص داخل إدراج المراجعات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام ميزة "Ignore Text Inside Insert Revisions" في Aspose.Words for .NET للتعامل مع مراجعات الإدراج في مستندات Word.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Ignore Text Inside Insert Revisions في Aspose.Words مكتبة .NET. هذه الميزة مفيدة عندما نريد تجاهل النص داخل إدراج المراجعات أثناء معالجة المستندات.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في معالجة النص داخل تنقيحات الإدخال ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: أدخل نصًا مع تتبع المراجعة

 بمجرد الحصول على مستند ، يمكننا إدراج نص مع تتبع المراجعة باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال ، لإدراج النص "المُدرج" مع تتبع المراجعة ، يمكننا استخدام`StartTrackRevisions`, `Writeln` و`StopTrackRevisions` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## الخطوة 3: أدخل نصًا لم تتم مراجعته

 بالإضافة إلى النص مع تتبع المراجعة ، يمكننا أيضًا إدراج نص غير منقح باستخدام امتداد`DocumentBuilder`هدف. على سبيل المثال ، لإدراج النص "نص" بدون مراجعة ، يمكننا استخدام`Write` طريقة:

```csharp
builder.Write("Text");
```

## الخطوة 4: استخدام وظيفة Ignore Text Inside Insert Revisions

 لتجاهل النص داخل إدراج المراجعات في العمليات اللاحقة ، يمكننا استخدام ملف`FindReplaceOptions` كائن وتعيين`IgnoreInserted` ملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## الخطوة 5: استخدام التعبيرات النمطية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص المستند ، سنستخدم التعبيرات العادية. في مثالنا ، سنبحث عن جميع تكرارات الحرف "e" ونستبدلها بعلامة النجمة "* ". سنستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 6: عرض إخراج المستند المعدل

بعد تطبيق البحث والاستبدال ، يمكننا عرض المحتوى الذي تم تغييره في المستند باستخدام`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 7: تغيير الخيارات لتضمين إدراج المراجعات

 إذا أردنا تضمين النص داخل مراجعات الإدراج في نتيجة الإخراج ، فيمكننا تغيير الخيارات لعدم تجاهل مراجعات الإدراج. لهذا سنقوم بتعيين`IgnoreInserted` ملكية ل`false`:

```csharp
options.IgnoreInserted = false;
```

## الخطوة 8: عرض المستند المعدل مع إدراج المراجعات

بعد تغيير الخيارات ، يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع النص الموجود داخل المراجعات المدرجة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### مثال على شفرة المصدر لـ Ignore Text Inside Insert Revisions باستخدام Aspose.Words for .NET

فيما يلي نموذج الكود المصدري الكامل لتوضيح استخدام وظيفة Ignore Text Inside Insert Revisions مع Aspose.Words for .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// أدخل النص مع تتبع المراجعات.
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

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Ignore Text Inside Insert Revisions في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند ، وإدخال نص مع مراجعات التعقب والنص غير المنقح ، واستخدام وظيفة Ignore Text Inside Insert Revisions ، وإجراء عمليات البحث واستبدال العمليات بالتعبيرات العادية ، وعرض المستند المعدل.