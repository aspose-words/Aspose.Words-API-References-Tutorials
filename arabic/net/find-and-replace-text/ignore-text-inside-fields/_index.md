---
title: تجاهل النص داخل الحقول
linktitle: تجاهل النص داخل الحقول
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام ميزة "تجاهل النص داخل الحقول" في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/ignore-text-inside-fields/
---
في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Ignore Text Inside Fields في مكتبة Aspose.Words for .NET. هذه الميزة مفيدة عندما نريد تجاهل النص داخل الحقول عند معالجة المستندات.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في معالجة النص داخل الحقول ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: إدخال حقل يحتوي على نص بداخله

 بمجرد أن نحصل على مستند ، يمكننا إدخال حقل يحتوي على نص بداخله باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال ، لإدراج حقل "INCLUDETEXT" مع النص "Text in field" ، يمكننا استخدام`InsertField` طريقة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## الخطوة 3: استخدام وظيفة Ignore Text Inside Fields

 لتجاهل النص داخل الحقول في العمليات اللاحقة ، يمكننا استخدام`FindReplaceOptions` كائن وتعيين`IgnoreFields` ملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## الخطوة 4: استخدام التعبيرات النمطية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص المستند ، سنستخدم التعبيرات العادية. في مثالنا ، سنبحث عن جميع تكرارات الحرف "e" ونستبدلها بعلامة النجمة "* ". سنستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 5: عرض إخراج المستند المعدل

بعد تطبيق البحث والاستبدال ، يمكننا عرض المحتوى الذي تم تغييره في المستند باستخدام`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 6: تغيير الخيارات لتضمين الحقول

نقوم بتضمين النص داخل الحقول في نتيجة الإخراج ، يمكننا تغيير الخيارات لعدم تجاهل الحقول. لهذا سنقوم بتعيين`IgnoreFields` ملكية ل`false`:

```csharp
options.IgnoreFields = false;
```

## الخطوة 7: عرض الوثيقة المعدلة مع الحقول

بعد تغيير الخيارات ، يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة بالنص الموجود داخل الحقول المضمنة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### مثال على شفرة المصدر لـ Ignore Text Inside Fields باستخدام Aspose.Words for .NET

إليك نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام وظيفة Ignore Text Inside Fields مع Aspose.Words for .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// أدخل الحقل مع النص بداخله.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Ignore Text Inside Fields في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند ، وإدخال حقل به نص بداخله ، واستخدام وظيفة Ignore Text Inside Fields ، وإجراء البحث واستبدال العمليات بالتعبيرات العادية ، وعرض المستند المعدل.

### التعليمات

#### س: ما هي ميزة "تجاهل النص داخل الحقول" في Aspose.Words for .NET؟

ج: ميزة "تجاهل النص داخل الحقول" في Aspose.Words for .NET تسمح لك بتحديد ما إذا كان يجب تجاهل النص الموجود داخل الحقول أثناء عمليات معينة ، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة ، لا يتم أخذ النص الموجود داخل الحقول في الاعتبار أثناء العمليات.

#### س: كيف يمكنني إنشاء مستند جديد باستخدام Aspose.Words for .NET؟

 ج: لإنشاء مستند جديد باستخدام Aspose.Words for .NET ، يمكنك إنشاء نسخة من ملف`Document` هدف. فيما يلي مثال على كود C # لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```

#### س: كيف يمكنني إدراج حقل به نص داخل مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد أن يكون لديك مستند ، يمكنك إدراج حقل به نص بداخله باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال ، لإدراج حقل "INCLUDETEXT" مع النص "Text in field" ، يمكنك استخدام`InsertField` طريقة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### س: كيف يمكنني تجاهل النص الموجود داخل الحقول في Aspose.Words for .NET؟

ج: لتجاهل النص داخل الحقول أثناء العمليات اللاحقة ، يمكنك استخدام ملف`FindReplaceOptions` كائن وتعيين`IgnoreFields` ملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### س: كيف يمكنني إجراء البحث والاستبدال باستخدام التعبيرات العادية في Aspose.Words for .NET؟

 ج: لإجراء عمليات البحث والاستبدال على نص المستند باستخدام التعبيرات العادية ، يمكنك استخدام .NET`Regex` فصل. على سبيل المثال ، للبحث عن جميع تكرارات الحرف "e" واستبدالها بعلامة النجمة "* "، يمكنك إنشاء ملف`Regex` الكائن واستخدامه مع`Replace` طريقة:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### س: كيف يمكنني عرض المخرجات المعدلة للوثيقة في Aspose.Words for .NET؟

 ج: بعد تطبيق عمليات البحث والاستبدال ، يمكنك عرض المحتوى الذي تم تغييره في المستند باستخدام ملف`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

#### س: كيف يمكنني تضمين الحقول في نتيجة الإخراج في Aspose.Words for .NET؟

 ج: لتضمين النص داخل الحقول في نتيجة الإخراج ، يمكنك تغيير الخيارات لعدم تجاهل الحقول. لهذا ، يمكنك ضبط ملف`IgnoreFields`ممتلكات`FindReplaceOptions` يعترض على`false`:

```csharp
options.IgnoreFields = false;
```

#### س: كيف يمكنني عرض المستند المعدل مع الحقول الموجودة في Aspose.Words for .NET؟

ج: بعد تغيير الخيارات لتضمين الحقول ، يمكنك إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة بالنص الموجود داخل الحقول المضمنة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```