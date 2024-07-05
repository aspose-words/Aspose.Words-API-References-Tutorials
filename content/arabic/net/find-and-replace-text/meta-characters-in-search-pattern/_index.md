---
title: أحرف التعريف في نمط البحث
linktitle: أحرف التعريف في نمط البحث
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام الأحرف الأولية في نمط البحث باستخدام Aspose.Words for .NET لمعالجة مستندات Word.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/meta-characters-in-search-pattern/
---
في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة Meta Characters In Search Pattern في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة استخدام أحرف أولية خاصة لإجراء عمليات بحث واستبدال متقدمة في مستندات Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في استخدام الأحرف الأولية في نمط البحث، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد حصولنا على مستند، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` و`Write` طرق لإدراج سطرين من النص:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## الخطوة 3: البحث عن النص واستبداله بالأحرف الأولية

 الآن سوف نستخدم`Range.Replace` وظيفة للبحث عن النص واستبداله باستخدام نمط بحث يحتوي على أحرف أولية خاصة. في مثالنا، نستبدل العبارة "هذا هو السطر 1&pهذا هو السطر 2" بعبارة "تم استبدال هذا السطر" باستخدام`&p` حرف أولي لتمثيل فاصل الفقرة:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## الخطوة 4: إدراج فاصل صفحات في المستند

 لتوضيح استخدام حرف أولي آخر، سنقوم بإدراج فاصل صفحات في المستند باستخدام الأمر`InsertBreak` الطريقة مع`BreakType.PageBreak` معامل. نقوم أولاً بتحريك المؤشر من`DocumentBuilder` إلى نهاية المستند، ثم نقوم بإدراج فاصل الصفحات وسطرًا جديدًا من النص:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## الخطوة 5: البحث عن حرف تعريف آخر واستبداله

 الآن سنقوم بإجراء بحث آخر واستبدال باستخدام`&m` حرف أولي لتمثيل فاصل الصفحات. نستبدل العبارة "هذا هو السطر 1&mهذا هو السطر 2" بعبارة "يتم استبدال فاصل الصفحات بنص جديد." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## الخطوة 6: حفظ المستند المحرر

وأخيرًا، نقوم بحفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### مثال على التعليمات البرمجية المصدر لأحرف التعريف في نمط البحث باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام الأحرف الأولية في نمط البحث باستخدام Aspose.Words for .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## خاتمة

في هذه المقالة، قمنا باستكشاف الكود المصدري لـ C# لفهم كيفية استخدام الأحرف الأولية في نمط البحث الخاص بـ Aspose.Words for .NET. لقد اتبعنا دليلاً خطوة بخطوة لإنشاء مستند، وإدراج نص، وإجراء البحث والاستبدال باستخدام أحرف أولية خاصة، وإدراج فواصل الصفحات، وحفظ المستند الذي تم تحريره.

### الأسئلة الشائعة

#### س: ما هي ميزة Meta Characters In Search Pattern في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة Meta Characters In Search Pattern في Aspose.Words for .NET استخدام أحرف تعريفية خاصة لإجراء عمليات بحث متقدمة واستبدالات في مستندات Word. تسمح لك هذه الأحرف الأولية بتمثيل فواصل الفقرات وفواصل الأقسام وفواصل الصفحات والعناصر الخاصة الأخرى في نمط البحث الخاص بك.

#### س: كيفية إنشاء مستند جديد في Aspose.Words لـ .NET؟

 ج: قبل استخدام الأحرف الأولية في قالب البحث، يجب عليك إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف. فيما يلي نموذج التعليمات البرمجية لإنشاء مستند جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### س: كيفية إدراج نص في مستند باستخدام Aspose.Words لـ .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` و`Write` طرق لإدراج سطرين من النص:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### س: كيف يتم البحث عن النص واستبداله بأحرف أولية في مستند باستخدام Aspose.Words for .NET؟

 ج: للبحث عن نص واستبداله بأحرف أولية، يمكنك استخدام`Range.Replace` طريقة. في مثالنا، نستبدل العبارة "هذا هو السطر 1&pهذا هو السطر 2" بعبارة "تم استبدال هذا السطر" باستخدام`&p` حرف أولي لتمثيل فاصل الفقرة:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### س: كيفية إدراج فاصل صفحات في مستند باستخدام Aspose.Words لـ .NET؟

ج: لتوضيح استخدام حرف أولي آخر، سنقوم بإدراج فاصل صفحات في المستند باستخدام الأمر`InsertBreak` الطريقة مع`BreakType.PageBreak` معامل. نقوم أولاً بتحريك المؤشر من`DocumentBuilder` إلى نهاية المستند، ثم نقوم بإدراج فاصل الصفحات وسطرًا جديدًا من النص:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### س: كيف يمكن البحث والاستبدال بحرف أولي آخر في مستند باستخدام Aspose.Words for .NET؟

 ج: سنقوم الآن بإجراء بحث آخر واستبداله باستخدام ملف`&m` حرف أولي لتمثيل فاصل الصفحات. نستبدل العبارة "هذا هو السطر 1&mهذا هو السطر 2" بعبارة "يتم استبدال فاصل الصفحات بنص جديد." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### س: كيف يتم حفظ المستند الذي تم تحريره في Aspose.Words لـ .NET؟

 ج: بمجرد إجراء تغييرات على المستند، يمكنك حفظه في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```