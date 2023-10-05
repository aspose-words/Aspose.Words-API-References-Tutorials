---
title: انطباق على الشبكة في مستند Word
linktitle: انطباق على الشبكة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لشرح كود مصدر C# الخاص بميزة Snap to Grid في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/snap-to-grid/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية استخدام ميزة Snap to Grid في مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء، قم بإنشاء مستند جديد وكائن DocumentBuilder مرتبط. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: محاذاة الشبكة

سنقوم الآن بتطبيق محاذاة الشبكة على فقرة معينة والخط المستخدم في الفقرة. إليك الطريقة:

```csharp
// تمكين محاذاة الشبكة للفقرة
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// كتابة النص في الفقرة
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// تمكين محاذاة الشبكة للخط المستخدم في الفقرة
par.Runs[0].Font.SnapToGrid = true;
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Snap To Grid باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة Snap to Grid مع Aspose.Words for .NET:

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

باستخدام هذا الرمز، ستتمكن من محاذاة النص الخاص بك مع الشبكة وتحسين مظهر مستندك باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي، استكشفنا عملية استخدام ميزة Snap to Grid في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك تمكين محاذاة الشبكة للفقرات والخطوط، مما يضمن تخطيط مستند جذابًا ومنظمًا بشكل جيد.

### الأسئلة الشائعة

#### س: ما هو Snap to Grid في مستند Word؟

ج: إن Snap to Grid عبارة عن ميزة في مستندات Word تعمل على محاذاة الكائنات، مثل النصوص والصور، إلى نظام الشبكة. ويضمن ذلك تحديد موضع دقيق ومحاذاة أنيقة، وهو أمر مفيد بشكل خاص عند التعامل مع التخطيطات المعقدة أو الأحرف الآسيوية.

#### س: كيف يعمل Snap to Grid على تحسين مظهر المستند؟

ج: يعمل Snap to Grid على تحسين مظهر المستند عن طريق الحفاظ على محاذاة متسقة للكائنات. فهو يمنع النص والعناصر الأخرى من الظهور بشكل غير صحيح أو متداخل، مما يؤدي إلى تخطيط احترافي ومصقول.

#### س: هل يمكنني تطبيق Snap to Grid على فقرات أو خطوط معينة في المستند الخاص بي؟

 ج: نعم، يمكنك تطبيق Snap to Grid على فقرات أو خطوط محددة في مستندك. من خلال تمكين`ParagraphFormat.SnapToGrid` و`Font.SnapToGrid` الخصائص، يمكنك التحكم في محاذاة الشبكة على أساس كل فقرة أو لكل خط.

#### س: هل Aspose.Words for .NET هو الحل الوحيد لـ Snap to Grid في مستندات Word؟

ج: يعد Aspose.Words for .NET أحد الحلول المتاحة لتنفيذ Snap to Grid في مستندات Word. توجد طرق وأدوات أخرى، لكن Aspose.Words for .NET يوفر واجهات برمجة تطبيقات وميزات قوية للعمل مع مستندات Word برمجيًا.

#### س: هل يمكنني استخدام Aspose.Words لـ .NET للعمل مع ميزات المستند الأخرى؟

ج: نعم، يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات للعمل مع مستندات Word. يتضمن وظائف لمعالجة النص وتخطيط الصفحة والجداول والصور والمزيد. يمكنك إنشاء مستندات Word وتعديلها وتحويلها باستخدام Aspose.Words لـ .NET.
