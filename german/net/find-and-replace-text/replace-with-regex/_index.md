---
title: استبدل بـ Regex
linktitle: استبدل بـ Regex
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إجراء استبدال النص المستند إلى التعبير العادي في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-with-regex/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة "استبدال بـ Regex" في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إجراء استبدال النص بناءً على أنماط معينة محددة بواسطة تعبير عادي.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام استبدال التعبير العادي ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

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

## الخطوة 3: تكوين خيارات البحث والاستبدال

 سنقوم الآن بتكوين خيارات البحث والاستبدال باستخدام ملف`FindReplaceOptions` هدف. في مثالنا ، نستخدم الخيارات الافتراضية:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## الخطوة 4: استبدل بالتعبير العادي

 نحن نستخدم ال`Range.Replace` طريقة لإجراء استبدال النص باستخدام تعبير عادي. في مثالنا ، نستخدم التعبير النمطي "[س|m]ad" to find the word秒 "Sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## الخطوة 5: حفظ المستند المعدل

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### مثال على شفرة المصدر لـ Replace With Regex باستخدام Aspose.Words for .NET

في ما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام استبدال التعبير العادي بـ Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام وظيفة "استبدال بـ Regex" في Aspose.Words لـ .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص وإجراء الاستبدال بتعبير عادي وحفظ المستند المعدل.
