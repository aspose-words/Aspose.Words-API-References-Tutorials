---
title: تغيير تباعد الفقرات الآسيوية والمسافات البادئة في مستند Word
linktitle: تغيير تباعد الفقرات الآسيوية والمسافات البادئة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تغيير تباعد الفقرات الآسيوية والمسافات البادئة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## الخطوة 2: تغيير تباعد الفقرات والمسافات البادئة

سنقوم الآن بتعديل المسافات والمسافات البادئة للفقرة الأولى من الوثيقة الآسيوية. إليك الطريقة:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // تحديث ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // تحديث ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //تحديث ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // قم بتحديث ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // تحديث ParagraphFormat.SpaceAfter
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### مثال على شفرة المصدر لتغيير المسافات والمسافات البادئة للفقرات الآسيوية باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة تحرير تباعد الفقرات والمسافات البادئة الآسيوية باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // سيتم تحديث ParagraphFormat.LeftIndent
	format.CharacterUnitRightIndent = 10;      // سيتم تحديث تنسيق الفقرة
	format.CharacterUnitFirstLineIndent = 20;  // سيتم تحديث ParagraphFormat.FirstLineIndent
	format.LineUnitBefore = 5;                 // سيتم تحديث ParagraphFormat.SpaceBefore
	format.LineUnitAfter = 10;                 // سيتم تحديث ParagraphFormat.SpaceAfter

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

باستخدام هذا الرمز ، ستتمكن من تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي ، تعلمنا كيفية تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET. عن طريق تعديل الخصائص ذات الصلة من`ParagraphFormat`، يمكننا التحكم في تخطيط ومظهر الفقرات الآسيوية في مستند Word. هذه الميزة مفيدة لتخصيص تنسيق النص بأحرف آسيوية وتحقيق العرض المرئي المطلوب في المستندات ذات المحتوى المختلط اللغات.

### التعليمات

#### س: ما الذي تفعله ميزة "تغيير تباعد الفقرات الآسيوية والمسافات البادئة" في Aspose.Words for .NET؟

ج: تسمح لك ميزة "تغيير تباعد الفقرات الآسيوية والمسافات البادئة" في Aspose.Words for .NET بتعديل خصائص التباعد والمسافة البادئة لفقرة آسيوية في مستند Word. يمكنك ضبط المسافة البادئة اليمنى واليسرى ، والمسافة البادئة للسطر الأول ، والمسافة قبل ، والمسافة بعد القيم للتحكم في تخطيط الفقرة ومظهرها.

#### س: كيف يمكنني تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET؟

 ج: لتغيير التباعد والمسافات البادئة لفقرة آسيوية ، تحتاج إلى الوصول إلى ملف`ParagraphFormat`من الفقرة الهدف وتعديل الخصائص ذات الصلة. في رمز المثال المقدم ، نصل إلى الفقرة الأولى من المستند وقمنا بتعيين ملف`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` ، و`LineUnitAfter` خصائص لضبط التباعد والمسافات البادئة.

#### س: هل يمكنني تطبيق هذه التغييرات على فقرات أخرى في المستند؟

 ج: نعم ، يمكنك تطبيق هذه التغييرات على فقرات أخرى في المستند من خلال الوصول إلى كل منها`ParagraphFormat` أشياء. يستهدف رمز المثال الفقرة الأولى من المستند ، ولكن يمكنك تعديل فقرات أخرى عن طريق ضبط الفهرس في ملف`Paragraphs` جمع أو استخدام معايير أخرى لتحديد الفقرات المطلوبة.