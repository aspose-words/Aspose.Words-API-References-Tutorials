---
title: أحرف التعريف في نمط البحث
linktitle: أحرف التعريف في نمط البحث
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام الحروف الأولية في نمط البحث باستخدام Aspose.Words for .NET لمعالجة مستندات Word.
type: docs
weight: 10
url: /es/net/find-and-replace-text/meta-characters-in-search-pattern/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Meta Characters In Search Pattern في Aspose.Words for .NET library. تتيح لك هذه الميزة استخدام أحرف أولية خاصة لإجراء عمليات بحث واستبدال متقدمة في مستندات Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام الحروف الأولية في نمط البحث ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نستخدم الامتداد`Writeln` و`Write` طرق لإدراج سطرين من النص:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## الخطوة 3: البحث عن النص واستبداله بأحرف أولية

 الآن سوف نستخدم ملف`Range.Replace` وظيفة للبحث عن نص واستبداله باستخدام نمط بحث يحتوي على أحرف أولية خاصة. في مثالنا ، نستبدل عبارة "This is line 1 & pThis is line 2" بـ "هذا السطر مستبدل" باستخدام`&p` الحرف الأولي لتمثيل فاصل فقرة:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## الخطوة 4: إدراج فاصل صفحة في المستند

 لتوضيح استخدام حرف أولي آخر ، سنقوم بإدراج فاصل صفحات في المستند باستخدام الامتداد`InsertBreak` الطريقة مع`BreakType.PageBreak` معامل. نحرك المؤشر أولاً من ملف`DocumentBuilder` في نهاية المستند ، ثم نقوم بإدخال فاصل الصفحة وسطر جديد من النص:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## الخطوة 5: ابحث عن حرف أولي آخر واستبدله

 سنقوم الآن بإجراء بحث آخر واستبداله باستخدام ملف`&m` الحرف الأولي لتمثيل فاصل صفحة. نستبدل العبارة "هذا هو السطر 1 و m هذا هو السطر 2" بعبارة "يتم استبدال فاصل الصفحة بنص جديد." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## الخطوة 6: حفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### مثال على شفرة المصدر لـ Meta Characters في نمط البحث باستخدام Aspose.Words for .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام الأحرف الأولية في نمط البحث مع Aspose.Words for .NET:

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

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام الحروف الأولية في نمط البحث في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص وإجراء بحث واستبدال باستخدام أحرف أولية خاصة وإدراج فواصل الصفحات وحفظ المستند المحرر.
