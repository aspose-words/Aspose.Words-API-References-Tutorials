---
title: استبدل النص الذي يحتوي على أحرف وصفية
linktitle: استبدل النص الذي يحتوي على أحرف وصفية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استبدال النص الذي يحتوي على أحرف أولية في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/replace-text-containing-meta-characters/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة استبدال النص الذي يحتوي على أحرف وصفية في Aspose.Words مكتبة .NET. تتيح لك هذه الميزة استبدال أجزاء من النص في مستند يحتوي على أحرف وصفية محددة.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام استبدال النص بأحرف أولية ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نستخدم الامتداد`Writeln`طريقة لإدراج فقرات نصية متعددة في أقسام مختلفة:

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

 سنقوم الآن بتكوين خيارات البحث والاستبدال باستخدام ملف`FindReplaceOptions` هدف. في مثالنا ، قمنا بتعيين محاذاة الفقرات المستبدلة إلى "توسيط":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment

.Center;
```

## الخطوة 4: استبدال النص الذي يحتوي على أحرف أولية

 نحن نستخدم ال`Range.Replace` طريقة لإجراء استبدال النص الذي يحتوي على أحرف أولية. في مثالنا ، نستبدل كل تكرار لكلمة "قسم" متبوعًا بفاصل فقرة بالكلمة نفسها متبوعة بعدة شرطات وفاصل فقرة جديد:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## الخطوة 5: استبدال علامة نصية مخصصة

 نستخدم أيضًا ملف`Range.Replace` طريقة لاستبدال العرف "{insert-section}"علامة نصية مع فاصل مقطعي. في مثالنا ، نستبدل"{insert-section}"مع & ب" لإدراج فاصل مقطعي:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## الخطوة 6: حفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### مثال على شفرة المصدر لاستبدال النص الذي يحتوي على أحرف وصفية باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح استخدام استبدال النص الذي يحتوي على أحرف أولية مع Aspose.Words for .NET:

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

	// ضاعف كل فاصل فقرة بعد كلمة "قسم" ، أضف نوعًا من التسطير واجعله في المنتصف.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// إدراج فاصل مقطعي بدلاً من علامة نصية مخصصة.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام ميزة استبدال النص الذي يحتوي على أحرف وصفية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص واستبدال نص يحتوي على أحرف أولية وحفظ المستند المعدل.

