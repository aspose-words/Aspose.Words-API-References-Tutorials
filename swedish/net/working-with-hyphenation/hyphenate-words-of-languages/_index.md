---
title: وصل كلمات اللغات
linktitle: وصل كلمات اللغات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية وصل الكلمات بلغات مختلفة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/hyphenate-words-of-languages/
---

في هذا البرنامج التعليمي المفصل خطوة بخطوة ، سنوجهك حول كيفية وصل الكلمات بلغات مختلفة في مستندات Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` عن طريق تحديد المسار إلى المستند المصدر الذي يحتوي على نص بلغات مختلفة:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## الخطوة 2: حفظ قواميس الواصلة

بعد ذلك ، احفظ قواميس الواصلة للغات المختلفة التي تريد معالجتها. في هذا المثال ، نسجل قواميس للغة الإنجليزية الأمريكية والألمانية السويسرية:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

تأكد من أن لديك ملفات القاموس المناسبة في دليل البيانات الخاص بك.

## الخطوة 3: معالجة الكلمات عن طريق الواصلة

 يمكنك الآن استخدام ميزات الواصلة لمعالجة الكلمات بلغات مختلفة. يمكنك استخدام طرق مختلفة لـ`Document` أو`DocumentBuilder`حسب احتياجاتك الخاصة.

```csharp
// مثال: استخدام أسلوب الواصلة في DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## الخطوة 4: احفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

لذا ! لقد نجحت في معالجة الكلمات عن طريق الواصلة بلغات مختلفة في مستند Word باستخدام Aspose.Words for .NET.

### عينة من التعليمات البرمجية المصدر لوصل الكلمات باستخدام Aspose.Words for .NET

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.
