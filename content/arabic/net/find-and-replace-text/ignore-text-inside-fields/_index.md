---
title: تجاهل النص داخل الحقول
linktitle: تجاهل النص داخل الحقول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام ميزة "تجاهل النص الموجود داخل الحقول" في Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/ignore-text-inside-fields/
---
في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة Ignore Text Inside Fields في مكتبة Aspose.Words for .NET. تكون هذه الميزة مفيدة عندما نريد تجاهل النص الموجود داخل الحقول عند التعامل مع المستندات.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في معالجة النص داخل الحقول، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: إدراج حقل به نص بداخله

 بمجرد حصولنا على مستند، يمكننا إدراج حقل يحتوي على نص بداخله باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج حقل "INCLUDETEXT" مع النص "النص في الحقل"، يمكننا استخدام`InsertField` طريقة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## الخطوة 3: استخدام وظيفة تجاهل النص داخل الحقول

 لتجاهل النص داخل الحقول في العمليات اللاحقة، يمكننا استخدام`FindReplaceOptions` الكائن وتعيين`IgnoreFields`الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## الخطوة 4: استخدام التعبيرات العادية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص المستند، سوف نستخدم التعبيرات العادية. في مثالنا، سوف نقوم بالبحث عن كافة تواجدات الحرف "e" واستبدالها بعلامة النجمة "* ". سوف نستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 5: عرض مخرجات المستند المعدل

 بعد تطبيق البحث والاستبدال، يمكننا عرض محتوى المستند الذي تم تغييره باستخدام ملف`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 6: تغيير الخيارات لتضمين الحقول

 نقوم بتضمين النص داخل الحقول في نتيجة الإخراج، يمكننا تغيير الخيارات لعدم تجاهل الحقول. لهذا سوف نقوم بتعيين`IgnoreFields`الملكية ل`false`:

```csharp
options.IgnoreFields = false;
```

## الخطوة 7: عرض المستند المعدل مع الحقول

بعد تغيير الخيارات يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة بالنص الموجود داخل الحقول المضمنة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### مثال على التعليمات البرمجية المصدر لتجاهل النص داخل الحقول باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام وظيفة Ignore Text Inside Fields مع Aspose.Words for .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// قم بإدراج حقل يحتوي على نص بداخله.
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

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة Ignore Text Inside Fields في Aspose.Words for .NET. لقد اتبعنا دليلًا خطوة بخطوة لإنشاء مستند، وإدراج حقل به نص بداخله، واستخدام وظيفة تجاهل النص داخل الحقول، وإجراء عمليات البحث والاستبدال بالتعبيرات العادية، وعرض المستند المعدل.

### الأسئلة الشائعة

#### س: ما هي ميزة "تجاهل النص الموجود داخل الحقول" في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة "تجاهل النص الموجود داخل الحقول" في Aspose.Words لـ .NET تحديد ما إذا كان يجب تجاهل النص الموجود داخل الحقول أثناء عمليات معينة، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة، لا يتم أخذ النص الموجود داخل الحقول في الاعتبار أثناء العمليات.

#### س: كيف يمكنني إنشاء مستند جديد باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء مستند جديد باستخدام Aspose.Words لـ .NET، يمكنك إنشاء مثيل`Document` هدف. فيما يلي مثال على كود C# لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```

#### س: كيف يمكنني إدراج حقل يحتوي على نص داخل مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج حقل يحتوي على نص بداخله باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال، لإدراج حقل "INCLUDETEXT" مع النص "النص الموجود في الحقل"، يمكنك استخدام`InsertField` طريقة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### س: كيف يمكنني تجاهل النص الموجود داخل الحقول في Aspose.Words لـ .NET؟

 ج: لتجاهل النص الموجود داخل الحقول أثناء العمليات اللاحقة، يمكنك استخدام ملف`FindReplaceOptions` الكائن وتعيين`IgnoreFields`الملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### س: كيف يمكنني تضمين الحقول في نتيجة الإخراج في Aspose.Words for .NET؟

 ج: لتضمين النص داخل الحقول في نتيجة الإخراج، يمكنك تغيير الخيارات لعدم تجاهل الحقول. لهذا يمكنك ضبط`IgnoreFields` ملكية`FindReplaceOptions` يعترض على`false`:

```csharp
options.IgnoreFields = false;
```

#### س: كيف يمكنني عرض المستند المعدل مع الحقول الموجودة في Aspose.Words لـ .NET؟

ج: بعد تغيير خيارات تضمين الحقول، يمكنك إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع النص الموجود داخل الحقول المضمنة:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```