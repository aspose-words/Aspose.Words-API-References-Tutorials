---
title: البحث عن نص بسيط واستبداله في Word
linktitle: البحث عن نص بسيط واستبداله في Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إجراء بحث بسيط عن نص واستبداله في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/simple-find-replace/
---
في هذه المقالة، سنستكشف الكود المصدري لـ C# أعلاه لفهم كيفية استخدام Simple Text Find And Replace في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إجراء استبدال بسيط للنص من خلال البحث عن سلسلة محددة من الأحرف واستبدالها بسلسلة أخرى من الأحرف في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في استخدام البحث والاستبدال البسيط، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد حصولنا على مستند، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` طريقة لإدراج عبارة "مرحبا_CustomerName_":"

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## الخطوة 3: استبدال النص البسيط

 نحن نستخدم ال`Range.Replace` طريقة لإجراء استبدال نص بسيط. في مثالنا، نقوم باستبدال كافة تكرارات السلسلة "_ClientName_ " مع "جيمس بوند" باستخدام`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: حفظ المستند المحرر

وأخيرًا، نقوم بحفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Simple Find Replace باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح استخدام البحث البسيط واستبداله بـ Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// احفظ المستند المعدل
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة Simple Find Replace الخاصة بـ Aspose.Words for .NET. لقد اتبعنا دليلاً خطوة بخطوة لإنشاء مستند وإدراج نص وإجراء استبدال بسيط للنص وحفظ المستند الذي تم تحريره.

### الأسئلة الشائعة

#### س: ما هي وظيفة البحث عن النص البسيط واستبداله في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة البحث عن النص البسيط واستبداله في Aspose.Words لـ .NET إجراء استبدال بسيط للنص في مستند Word. يسمح لك بالبحث عن سلسلة أحرف محددة واستبدالها بسلسلة أحرف أخرى. قد يكون هذا مفيدًا عندما تريد إجراء تغييرات عامة على مستند، مثل استبدال الأسماء أو التواريخ أو المعلومات الأخرى.

#### س: كيفية إنشاء مستند جديد في Aspose.Words لـ .NET؟

 ج: قبل استخدام وظيفة Simple Text Find And Replace، يجب عليك إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف. فيما يلي نموذج التعليمات البرمجية لإنشاء مستند جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### س: كيفية إدراج نص في مستند باستخدام Aspose.Words لـ .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` طريقة لإدراج عبارة "مرحبا_CustomerName_:::

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### س: كيف يمكنني إجراء استبدال بسيط للنص في مستند باستخدام Aspose.Words for .NET؟

 ج: لإجراء استبدال بسيط للنص، يمكنك استخدام`Range.Replace` طريقة. في مثالنا، نقوم باستبدال كافة تكرارات السلسلة "_ClientName_ " مع "جيمس بوند" باستخدام`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: كيف يتم حفظ المستند الذي تم تحريره في Aspose.Words لـ .NET؟

 ج: بمجرد الانتهاء من استبدال النص، يمكنك حفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```