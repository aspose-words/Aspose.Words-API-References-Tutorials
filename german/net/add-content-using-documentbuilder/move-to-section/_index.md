---
title: الانتقال إلى القسم
linktitle: الانتقال إلى القسم
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لاستخدام Move To Section في Aspose.Words for .NET يعالج الأقسام والفقرات في مستندات Word.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-section/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة Move To Section في Aspose.Words for .NET خطوة بخطوة باستخدام كود المصدر C # المقدم. تتيح لك هذه الميزة التنقل والتعامل مع الأقسام المختلفة داخل مستند Word. اتبع الخطوات أدناه لدمج هذه الوظيفة في تطبيقك.

## الخطوة 1: قم بإنشاء مستند جديد وإضافة قسم

أولاً ، نحتاج إلى إنشاء مستند جديد وإضافة قسم إليه. استخدم الكود التالي لإنجاز هذه الخطوة:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

ينشئ هذا الرمز مستندًا فارغًا جديدًا ويضيف قسمًا إلى هذا المستند.

## الخطوة 2: انقل DocumentBuilder إلى القسم الثاني وأضف نصًا

بعد ذلك ، نحتاج إلى نقل DocumentBuilder إلى القسم الثاني من المستند وإضافة بعض النص هناك. استخدم الكود التالي لإجراء هذه الخطوة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

ينشئ هذا الرمز DocumentBuilder من المستند الموجود ، ثم ينقل المؤشر من DocumentBuilder إلى القسم الثاني من المستند. أخيرًا ، يضيف النص المحدد إلى هذا القسم.

## الخطوة 3: تحميل مستند بالفقرات الموجودة

إذا كنت تريد العمل مع مستند موجود يحتوي على فقرات ، فيمكنك تحميل هذا المستند باستخدام الكود التالي:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

يقوم هذا الرمز بتحميل المستند المحدد (استبدل "MyDir +" Paragraphs.docx“”بالمسار الفعلي إلى المستند الخاص بك) والوصول إلى مجموعة الفقرات من القسم الأول من المستند. الخط`Assert.AreEqual(22, paragraphs.Count);` يتحقق من أن المستند يحتوي على 22 فقرة.

## الخطوة 4: إنشاء DocumentBuilder لمستند

يمكنك إنشاء مؤشر DocumentBuilder على فقرة معينة باستخدام المؤشرات الموضعية.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## الخطوة 5: حرك المؤشر إلى فقرة معينة


يمكنك تحريك مؤشر DocumentBuilder إلى فقرة معينة باستخدام المؤشرات الموضعية. هيريس كيفية القيام بذلك:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

يقوم هذا الرمز بنقل مؤشر DocumentBuilder إلى الفقرة الثالثة من القسم الثاني (الفقرة في الفهرس 2) وإلى الموضع 10. ثم يضيف فقرة جديدة مع بعض النص ويتحقق من وضع المؤشر بشكل جيد على هذه الفقرة الجديدة.

### مثال على شفرة المصدر لـ Move To Move To Section باستخدام Aspose.Words for .NET

```csharp

	
	Document doc = new Document();
	doc.AppendChild(new Section(doc));

	// انقل DocumentBuilder إلى القسم الثاني وأضف نصًا.
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToSection(1);
	builder.Writeln("Text added to the 2nd section.");

	// إنشاء وثيقة مع فقرات.
	doc = new Document(MyDir + "Paragraphs.docx");
	ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
	Assert.AreEqual(22, paragraphs.Count);

	//عندما نقوم بإنشاء DocumentBuilder لمستند ، يكون المؤشر في بداية المستند افتراضيًا ،
	// وسيتم إضافة أي محتوى مضاف بواسطة DocumentBuilder إلى المستند.
	builder = new DocumentBuilder(doc);
	Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

	// يمكنك تحريك المؤشر إلى أي موضع في الفقرة.
	builder.MoveToParagraph(2, 10);
	Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
	builder.Writeln("This is a new third paragraph. ");
	Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
	
        
```

هذا كل شئ ! لقد فهمت الآن كيفية استخدام وظيفة الانتقال إلى قسم Aspose.Words for .NET باستخدام كود المصدر المقدم. يمكنك الآن دمج هذه الوظيفة في التطبيق الخاص بك ومعالجة أقسام وفقرات مستندات Word بشكل ديناميكي.

