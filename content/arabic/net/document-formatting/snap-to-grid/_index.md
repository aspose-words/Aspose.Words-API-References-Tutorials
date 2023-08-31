---
title: انجذاب إلى الشبكة في مستند Word
linktitle: انجذاب إلى الشبكة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لشرح كود مصدر C # لـ Snap to Grid في ميزة مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/snap-to-grid/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام ميزة Snap to Grid في مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: محاذاة الشبكة

سنقوم الآن بتطبيق محاذاة الشبكة على فقرة محددة والخط المستخدم في الفقرة. إليك الطريقة:

```csharp
// تمكين محاذاة الشبكة للفقرة
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// اكتب نصًا في الفقرة
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// قم بتمكين محاذاة الشبكة للخط المستخدم في الفقرة
par.Runs[0].Font.SnapToGrid = true;
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### مثال على شفرة المصدر لـ Snap To Grid باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة Snap to Grid مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// قم بتحسين التخطيط عند الكتابة بالأحرف الآسيوية.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

باستخدام هذا الرمز ، ستتمكن من محاذاة النص الخاص بك مع الشبكة وتحسين مظهر المستند باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، استكشفنا عملية استخدام ميزة Snap to Grid في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك تمكين محاذاة الشبكة للفقرات والخطوط ، مما يضمن تخطيط مستند جيد التنظيم وممتع بصريًا.

### التعليمات

#### س: ما المقصود بـ Snap to Grid في مستند Word؟

ج: الانجذاب إلى الشبكة هي ميزة في مستندات Word تعمل على محاذاة الكائنات ، مثل النصوص والصور ، إلى نظام الشبكة. يضمن ذلك تحديد الموضع بدقة ومحاذاة أنيقة ، وهو مفيد بشكل خاص عند التعامل مع التخطيطات المعقدة أو الأحرف الآسيوية.

#### س: كيف يحسن Snap to Grid مظهر المستند؟

ج: يحسن الانجذاب إلى الشبكة مظهر المستند عن طريق الحفاظ على محاذاة متسقة للكائنات. يمنع النص والعناصر الأخرى من الظهور بشكل غير محاذي أو متداخل ، مما ينتج عنه تخطيط احترافي ومصقول.

#### س: هل يمكنني تطبيق Snap to Grid على فقرات أو خطوط معينة في المستند الخاص بي؟

 ج: نعم ، يمكنك تطبيق Snap to Grid على فقرات أو خطوط معينة في وثيقتك. من خلال تمكين`ParagraphFormat.SnapToGrid` و`Font.SnapToGrid` الخصائص ، يمكنك التحكم في محاذاة الشبكة على أساس كل فقرة أو لكل خط.

#### س: هل Aspose.Words for .NET الحل الوحيد لـ Snap to Grid في مستندات Word؟

ج: Aspose.Words for .NET هو أحد الحلول المتاحة لتطبيق Snap to Grid في مستندات Word. هناك طرق وأدوات أخرى ، ولكن Aspose.Words for .NET توفر واجهات برمجة تطبيقات قوية وميزات للعمل مع مستندات Word برمجيًا.

#### س: هل يمكنني استخدام Aspose.Words لـ .NET للعمل مع ميزات المستندات الأخرى؟

ج: نعم ، تقدم Aspose.Words for .NET مجموعة كبيرة من الميزات للعمل مع مستندات Word. يتضمن وظائف لمعالجة النص وتخطيط الصفحة والجداول والصور والمزيد. يمكنك إنشاء مستندات Word وتعديلها وتحويلها باستخدام Aspose.Words for .NET.
