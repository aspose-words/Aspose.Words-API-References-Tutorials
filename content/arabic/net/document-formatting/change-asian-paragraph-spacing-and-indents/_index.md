---
title: تغيير تباعد الفقرات الآسيوية والمسافات البادئة في مستند Word
linktitle: تغيير تباعد الفقرات الآسيوية والمسافات البادئة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تغيير تباعد الفقرات والمسافات البادئة الآسيوية في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تغيير التباعد والمسافات البادئة للفقرة الآسيوية باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق التغييرات.

## الخطوة 1: تحميل الوثيقة

للبدء، حدد الدليل الخاص بمستنداتك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن Document. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## الخطوة 2: تغيير تباعد الفقرات والمسافات البادئة

سنقوم الآن بتعديل التباعد والمسافات البادئة للفقرة الأولى من الوثيقة الآسيوية. إليك الطريقة:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // تحديث ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // تحديث ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //تحديث ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // تحديث ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // تحديث ParagraphFormat.SpaceAfter
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### مثال على التعليمات البرمجية المصدر لتغيير تباعد الفقرات والمسافات البادئة باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة تحرير تباعد الفقرات الآسيوية والمسافات البادئة باستخدام Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // سيتم تحديث ParagraphFormat.LeftIndent
	format.CharacterUnitRightIndent = 10;      // سيتم تحديث ParagraphFormat.RightIndent
	format.CharacterUnitFirstLineIndent = 20;  // سيتم تحديث ParagraphFormat.FirstLineIndent
	format.LineUnitBefore = 5;                 // سيتم تحديث ParagraphFormat.SpaceBefore
	format.LineUnitAfter = 10;                 // سيتم تحديث ParagraphFormat.SpaceAfter

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

باستخدام هذا الرمز، ستتمكن من تغيير التباعد والمسافات البادئة للفقرة الآسيوية باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي، تعلمنا كيفية تغيير التباعد والمسافات البادئة للفقرة الآسيوية باستخدام Aspose.Words for .NET. عن طريق تعديل الخصائص ذات الصلة لـ`ParagraphFormat`، يمكننا التحكم في تخطيط ومظهر الفقرات الآسيوية في مستند Word. تعد هذه الميزة مفيدة لتخصيص تنسيق النص بأحرف آسيوية وتحقيق العرض المرئي المطلوب في المستندات ذات المحتوى اللغوي المختلط.

### الأسئلة الشائعة

#### س: ما الذي تفعله ميزة "تغيير تباعد الفقرات والمسافات البادئة الآسيوية" في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة "تغيير تباعد الفقرات الآسيوية والمسافات البادئة" في Aspose.Words لـ .NET تعديل خصائص التباعد والمسافات البادئة للفقرة الآسيوية في مستند Word. يمكنك ضبط المسافات البادئة اليمنى واليسرى، والمسافة البادئة للسطر الأول، والمسافة قبل، والمسافة بعد القيم للتحكم في تخطيط الفقرة ومظهرها.

#### س: كيف يمكنني تغيير التباعد والمسافات البادئة للفقرة الآسيوية باستخدام Aspose.Words لـ .NET؟

 ج: لتغيير التباعد والمسافات البادئة للفقرة الآسيوية، تحتاج إلى الوصول إلى`ParagraphFormat`للفقرة المستهدفة وتعديل خصائصها ذات الصلة. في رمز المثال المقدم، نصل إلى الفقرة الأولى من المستند ونقوم بتعيين`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` ، و`LineUnitAfter` خصائص لضبط التباعد والمسافات البادئة.

#### س: هل يمكنني تطبيق هذه التغييرات على فقرات أخرى في المستند؟

 ج: نعم، يمكنك تطبيق هذه التغييرات على فقرات أخرى في المستند عن طريق الوصول إلى كل منها`ParagraphFormat` أشياء. يستهدف رمز المثال الفقرة الأولى من المستند، ولكن يمكنك تعديل الفقرات الأخرى عن طريق ضبط الفهرس في ملف`Paragraphs` جمع أو استخدام معايير أخرى لاختيار الفقرات المطلوبة.