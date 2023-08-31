---
title: الانتقال إلى الرؤوس والتذييلات في مستند Word
linktitle: الانتقال إلى الرؤوس والتذييلات في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام Aspose.Words for .NET للتنقل وتعديل الرؤوس والتذييلات في مستندات Word باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-headers-footers/
---
في هذا المثال، سوف نستكشف ميزة النقل إلى تذييلات الرؤوس في Aspose.Words لـ .NET. Aspose.Words هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word وتعديلها وتحويلها برمجيًا. تتيح لنا ميزة "الانتقال إلى الرؤوس/التذييلات" إمكانية التنقل إلى الرؤوس والتذييلات المختلفة داخل المستند وإضافة محتوى إليها.

فلنستعرض التعليمات البرمجية المصدر خطوة بخطوة لفهم كيفية استخدام ميزة "الانتقال إلى الرؤوس/التذييلات" باستخدام Aspose.Words for .NET.

## الخطوة 1: تهيئة المستند ومنشئ المستندات

أولاً، قم بتهيئة كائنات Document وDocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين الرؤوس والتذييلات

حدد إعدادات الرأس/التذييل للمستند. في هذا المثال، قمنا بتعيين الرؤوس والتذييلات لتكون مختلفة للصفحة الأولى وللصفحات الفردية/الزوجية:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## الخطوة 3: إنشاء رؤوس لصفحات مختلفة

انتقل إلى كل نوع رأس وأضف محتوى إليه. في هذا المثال، نقوم بإنشاء رؤوس للصفحة الأولى، والصفحات الزوجية، وجميع الصفحات الأخرى:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## الخطوة 4: إنشاء صفحات في المستند
أضف محتوى إلى المستند لإنشاء صفحات متعددة. على سبيل المثال:

```csharp
// قم بإنشاء صفحتين في المستند.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## الخطوة 5: حفظ الوثيقة

احفظ المستند المعدل في الموقع المطلوب:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

تأكد من تحديد مسار الملف وتنسيقه المناسبين (مثل DOCX).

### مثال على التعليمات البرمجية المصدر للانتقال إلى الرؤوس/التذييلات باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//حدد أننا نريد أن تكون الرؤوس والتذييلات مختلفة للصفحات الأولى والزوجية والفردية.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// قم بإنشاء الرؤوس.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// قم بإنشاء صفحتين في المستند.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## خاتمة

في هذا المثال، اكتشفنا ميزة النقل إلى الرؤوس/التذييلات في Aspose.Words لـ .NET. لقد تعلمنا كيفية التنقل إلى الرؤوس والتذييلات المختلفة داخل مستند Word وإضافة محتوى إليها باستخدام فئة DocumentBuilder. تسمح هذه الميزة للمطورين بتخصيص الرؤوس والتذييلات لصفحات أو أقسام محددة، مما يوفر المرونة في إنشاء مستندات احترافية ومنظمة. يوفر Aspose.Words for .NET مجموعة قوية من الأدوات لمعالجة مستندات Word برمجيًا، مما يجعلها مكتبة أساسية لتطبيقات معالجة المستندات.

### الأسئلة المتداولة حول الانتقال إلى الرؤوس والتذييلات في مستند Word

#### س: ما هو الغرض من ميزة النقل إلى الرؤوس/التذييلات في Aspose.Words لـ .NET؟

ج: تتيح ميزة "الانتقال إلى الرؤوس/التذييلات" في Aspose.Words for .NET للمطورين إمكانية التنقل إلى الرؤوس والتذييلات المختلفة داخل مستند Word وإضافة محتوى إليها برمجيًا. يكون ذلك مفيدًا عندما تحتاج إلى تخصيص الرؤوس والتذييلات لصفحات أو أقسام مختلفة في المستند.

#### س: هل يمكنني الحصول على رؤوس وتذييلات مختلفة لصفحات مختلفة في المستند؟

ج: نعم، يمكنك تحديد رؤوس وتذييلات مختلفة للصفحة الأولى، والصفحات الزوجية، والصفحات الفردية باستخدام خصائص PageSetup.DifferentFirstPageHeaderFooter وPageSetup.OddAndEvenPagesHeaderFooter، على التوالي.

#### س: كيف يمكنني إضافة محتوى إلى رؤوس وتذييلات محددة؟

ج: لإضافة محتوى إلى رؤوس وتذييلات محددة، استخدم أسلوب MoveToHeaderFooter للفئة DocumentBuilder. يمكنك الانتقال إلى الرؤوس HeaderFirst وHeaderEven وHeaderPrimary أو تذييلات FooterFirst وFooterEven وFooterPrimary بناءً على متطلباتك.

#### س: هل يمكنني إنشاء رؤوس وتذييلات لقسم معين في المستند؟

ج: نعم، يمكنك استخدام أسلوب MoveToSection لفئة DocumentBuilder للانتقال إلى قسم معين في المستند ثم إنشاء رؤوس وتذييلات داخل هذا القسم.

#### س: كيف يمكنني حفظ المستند المعدل في ملف باستخدام Aspose.Words for .NET؟

ج: يمكنك حفظ المستند المعدل في الموقع والتنسيق المطلوب باستخدام أسلوب الحفظ الخاص بفئة المستند. تأكد من تحديد مسار الملف المناسب وتنسيق الملف (مثل DOCX).