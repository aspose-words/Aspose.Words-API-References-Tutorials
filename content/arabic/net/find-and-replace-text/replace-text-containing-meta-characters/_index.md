---
title: يقوم Word باستبدال النص الذي يحتوي على أحرف التعريف
linktitle: يقوم Word باستبدال النص الذي يحتوي على أحرف التعريف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استبدال النص الذي يحتوي على أحرف أولية في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-text-containing-meta-characters/
---
في هذه المقالة، سنستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة Word Replace Text Containing Meta Characters في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة استبدال أجزاء من النص في مستند يحتوي على أحرف تعريفية محددة.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في استخدام استبدال نص الأحرف الأولية، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد حصولنا على مستند، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` طريقة لإدراج فقرات متعددة من النص في أقسام مختلفة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## الخطوة 3: تكوين خيارات البحث والاستبدال

 سنقوم الآن بتكوين خيارات البحث والاستبدال باستخدام ملف`FindReplaceOptions` هدف. في مثالنا، قمنا بتعيين محاذاة الفقرات المستبدلة إلى "توسيط":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## الخطوة 4: استبدال النص الذي يحتوي على أحرف أولية

 نحن نستخدم ال`Range.Replace`طريقة لإجراء استبدال النص الذي يحتوي على أحرف أولية. في مثالنا، نستبدل كل تكرار لكلمة "قسم" متبوعًا بفاصل فقرة بنفس الكلمة متبوعة بعدة شرطات وفاصل فقرة جديد:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## الخطوة 5: استبدال علامة نصية مخصصة

 نحن نستخدم أيضًا`Range.Replace` طريقة لاستبدال مخصص "{insert-section}"علامة نصية تحتوي على فاصل مقطعي. في مثالنا، قمنا باستبدال "{insert-section}" مع "&b" لإدراج فاصل مقطعي:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## الخطوة 6: حفظ المستند المحرر

 وأخيرًا، نقوم بحفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### مثال على التعليمات البرمجية المصدر لاستبدال النص الذي يحتوي على أحرف التعريف باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح استخدام استبدال النص الذي يحتوي على أحرف أولية باستخدام Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// ضاعف فاصل كل فقرة بعد كلمة "قسم"، وأضف نوعًا من التسطير واجعله في المنتصف.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// قم بإدراج فاصل مقطعي بدلاً من علامة النص المخصصة.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام ميزة استبدال النص الذي يحتوي على أحرف التعريف في Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لإنشاء مستند وإدراج نص واستبدال النص الذي يحتوي على أحرف أولية وحفظ المستند المعدل.

### الأسئلة الشائعة

#### س: ما هي وظيفة استبدال النص الذي يحتوي على أحرف التعريف في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة استبدال النص الذي يحتوي على أحرف التعريف في Aspose.Words لـ .NET استبدال أجزاء من النص في مستند يحتوي على أحرف تعريف محددة. يمكنك استخدام هذه الميزة لإجراء عمليات استبدال متقدمة في مستندك مع مراعاة الأحرف الأولية.

#### س: كيفية إنشاء مستند جديد في Aspose.Words لـ .NET؟

 ج: قبل استخدام وظيفة استبدال النص الذي يحتوي على أحرف التعريف، يجب عليك إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف. فيما يلي نموذج التعليمات البرمجية لإنشاء مستند جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### س: كيفية إدراج نص في مستند باستخدام Aspose.Words لـ .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` طريقة لإدراج فقرات متعددة من النص في أقسام مختلفة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### س: كيفية تكوين خيارات البحث والاستبدال في Aspose.Words لـ .NET؟

 ج: الآن سنقوم بتكوين خيارات البحث والاستبدال باستخدام ملف`FindReplaceOptions` هدف. في مثالنا، قمنا بتعيين محاذاة الفقرات المستبدلة إلى "توسيط":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### س: كيف يمكن استبدال النص الذي يحتوي على أحرف أولية في مستند باستخدام Aspose.Words لـ .NET؟

 ج: نستخدم`Range.Replace` طريقة لإجراء استبدال النص الذي يحتوي على أحرف وصفية. في مثالنا، نستبدل كل تكرار لكلمة "قسم" متبوعًا بفاصل فقرة بنفس الكلمة متبوعة بعدة شرطات وفاصل فقرة جديد:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### س: كيف يمكن استبدال علامة نصية مخصصة تحتوي على أحرف تعريفية في مستند باستخدام Aspose.Words لـ .NET؟

 ج: نستخدم أيضًا`Range.Replace` طريقة لاستبدال مخصص "{insert-section}"علامة نصية تحتوي على فاصل مقطعي. في مثالنا، قمنا باستبدال "{insert-section}" مع "&b" لإدراج فاصل مقطعي:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### س: كيف يتم حفظ المستند الذي تم تحريره في Aspose.Words لـ .NET؟

 ج: بمجرد إجراء تغييرات على المستند، يمكنك حفظه في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```