---
title: الانتقال إلى القسم في مستند Word
linktitle: الانتقال إلى القسم في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لاستخدام ميزة النقل إلى القسم في مستند Word في Aspose.Words لـ .NET يتعامل مع الأقسام والفقرات في مستندات Word.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-section/
---
في هذا المثال، سنرشدك إلى كيفية استخدام ميزة النقل إلى القسم في مستند Word الخاصة بـ Aspose.Words لـ .NET خطوة بخطوة باستخدام كود مصدر C# المقدم. تتيح لك هذه الميزة التنقل بين الأقسام المختلفة ومعالجتها داخل مستند Word. اتبع الخطوات أدناه لدمج هذه الوظيفة في التطبيق الخاص بك.

## الخطوة 1: إنشاء مستند جديد وإضافة قسم

أولاً، نحتاج إلى إنشاء مستند جديد وإضافة قسم إليه. استخدم الكود التالي لإنجاز هذه الخطوة:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

يقوم هذا الرمز بإنشاء مستند فارغ جديد وإضافة قسم إلى هذا المستند.

## الخطوة 2: انقل DocumentBuilder إلى القسم الثاني وأضف نصًا

بعد ذلك، نحتاج إلى نقل DocumentBuilder إلى القسم الثاني من المستند وإضافة بعض النص هناك. استخدم الكود التالي لتنفيذ هذه الخطوة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

يقوم هذا الرمز بإنشاء DocumentBuilder من المستند الموجود، ثم ينقل المؤشر من DocumentBuilder إلى القسم الثاني من المستند. وأخيرا، فإنه يضيف النص المحدد إلى هذا القسم.

## الخطوة 3: قم بتحميل مستند بالفقرات الموجودة

إذا كنت تريد العمل مع مستند موجود يحتوي على فقرات، فيمكنك تحميل هذا المستند باستخدام الكود التالي:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

يقوم هذا الرمز بتحميل المستند المحدد (استبدل "MyDir + "Paragraphs.docx"" بالمسار الفعلي للمستند الخاص بك) والوصول إلى مجموعة الفقرات من القسم الأول من المستند. الخط`Assert.AreEqual(22, paragraphs.Count);` التحقق من أن المستند يحتوي على 22 فقرة.

## الخطوة 4: إنشاء DocumentBuilder للمستند

يمكنك إنشاء مؤشر DocumentBuilder لفقرة معينة باستخدام الفهارس الموضعية.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## الخطوة 5: نقل المؤشر إلى فقرة محددة


يمكنك نقل مؤشر DocumentBuilder إلى فقرة معينة باستخدام الفهارس الموضعية. هيريس كيفية القيام بذلك:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

يقوم هذا الرمز بنقل مؤشر DocumentBuilder إلى الفقرة الثالثة من القسم الثاني (الفقرة في الفهرس 2) وإلى الموضع 10. ثم يضيف فقرة جديدة تحتوي على بعض النص ويتحقق من وضع المؤشر بشكل جيد على هذه الفقرة الجديدة.

### مثال على التعليمات البرمجية المصدر لـ Move To Move To section باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// انقل DocumentBuilder إلى القسم الثاني وأضف نصًا.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// إنشاء وثيقة مع الفقرات.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// عندما نقوم بإنشاء DocumentBuilder لمستند ما، يكون المؤشر الخاص به في بداية المستند افتراضيًا،
// وأي محتوى تمت إضافته بواسطة DocumentBuilder سيتم إضافته مسبقًا إلى المستند.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//يمكنك تحريك المؤشر إلى أي موضع في الفقرة.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

هذا كل شئ ! لقد فهمت الآن كيفية استخدام وظيفة النقل إلى القسم في Aspose.Words لـ .NET باستخدام كود المصدر المقدم. يمكنك الآن دمج هذه الوظيفة في تطبيقك الخاص ومعالجة الأقسام والفقرات في مستندات Word الخاصة بك ديناميكيًا.

## خاتمة

في هذا المثال، قمنا باستكشاف ميزة النقل إلى القسم في Aspose.Words لـ .NET. لقد تعلمنا كيفية إنشاء مستند جديد وإضافة أقسام إليه واستخدام فئة DocumentBuilder للانتقال إلى أقسام وفقرات محددة داخل مستند Word. توفر هذه الميزة للمطورين أدوات قوية للتعامل مع محتوى وبنية مستندات Word برمجيًا باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة للانتقال إلى القسم في مستند Word

#### س: ما هو الغرض من ميزة النقل إلى القسم في Aspose.Words لـ .NET؟

ج: تتيح ميزة "الانتقال إلى القسم" في Aspose.Words for .NET للمطورين إمكانية التنقل إلى الأقسام المختلفة ومعالجتها داخل مستند Word برمجيًا. فهو يوفر القدرة على إدراج المحتوى أو تعديله أو حذفه في أقسام معينة من المستند.

#### س: كيف يمكنني نقل DocumentBuilder إلى قسم معين في مستند Word؟

ج: لنقل DocumentBuilder إلى قسم معين في مستند Word، يمكنك استخدام أسلوب MoveToSection لفئة DocumentBuilder. تأخذ هذه الطريقة فهرس القسم المستهدف كمعلمة وتضع المؤشر في بداية هذا القسم.

#### س: هل يمكنني إضافة محتوى أو تعديله بعد الانتقال إلى قسم معين باستخدام ميزة النقل إلى القسم؟

ج: نعم، بمجرد وضع DocumentBuilder في القسم المطلوب باستخدام MoveToSection، يمكنك استخدام طرق مختلفة لفئة DocumentBuilder، مثل Writeln أو Write أو InsertHtml، لإضافة محتوى هذا القسم أو تعديله.

#### س: كيف يمكنني العمل مع الفقرات الموجودة في المستند باستخدام ميزة النقل إلى القسم؟

ج: يمكنك تحميل مستند موجود يحتوي على فقرات باستخدام مُنشئ المستند ثم الوصول إلى مجموعة الفقرات من القسم المطلوب باستخدام خاصية FirstSection.Body.Paragraphs.

#### س: هل يمكنني نقل مؤشر DocumentBuilder إلى فقرة معينة داخل قسم ما باستخدام ميزة النقل إلى القسم؟

ج: نعم، يمكنك نقل مؤشر DocumentBuilder إلى فقرة معينة داخل القسم باستخدام الأسلوب MoveToParagraph. تأخذ هذه الطريقة مؤشرات الفقرة المستهدفة وموضع الحرف (الإزاحة) داخل الفقرة كمعلمات.