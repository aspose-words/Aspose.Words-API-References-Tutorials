---
title: استبدل بسلسلة
linktitle: استبدل بسلسلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استبدال النص بسلسلة في مستند Word بـ Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-with-string/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة "استبدال السلسلة" في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إجراء استبدال النص بناءً على سلسلة أحرف معينة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

قبل أن نبدأ في استخدام استبدال السلسلة ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نستخدم الامتداد`Writeln` طريقة ادخال عبارة "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## الخطوة 3: استبدل بسلسلة

 نحن نستخدم ال`Range.Replace` طريقة لاستبدال النص بسلسلة. في مثالنا ، نستبدل كل تكرارات كلمة "sad" بكلمة "bad" باستخدام الامتداد`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: حفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### مثال على شفرة المصدر لـ Replace With String باستخدام Aspose.Words for .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام الاستبدال بسلسلة أحرف بـ Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Replace With String في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص واستبداله بسلسلة وحفظ المستند المعدل.
