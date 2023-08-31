---
title: تنسيق الفقرة في مستند Word
linktitle: تنسيق الفقرة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تطبيق التنسيق المخصص على فقراتك في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/paragraph-formatting/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام تنسيق الفقرة في ميزة مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تنسيق الفقرة

سنقوم الآن بتطبيق التنسيق على الفقرة باستخدام الخصائص المتاحة في كائن ParagraphFormat من كائن DocumentBuilder. إليك الطريقة:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### مثال على شفرة المصدر لتنسيق الفقرة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة تنسيق الفقرة باستخدام Aspose.Words for .NET:


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat.LeftIndent = 50;
paragraphFormat.RightIndent = 50;
paragraphFormat.SpaceAfter = 25;

builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");

```

باستخدام هذا الرمز ، ستتمكن من تطبيق تنسيقات مختلفة على فقراتك باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، استكشفنا عملية استخدام ميزة تنسيق الفقرة في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك تنسيق فقراتك بشكل فعال ، وضبط محاذاةها ، والمسافات البادئة ، والتباعد لإنشاء مستندات جذابة بصريًا وذات تنظيم جيد.

### أسئلة وأجوبة

#### س: ما هو تنسيق الفقرة في مستند Word؟

ج: يشير تنسيق الفقرة إلى التخصيص المرئي للفقرات الفردية في مستند Word. يتضمن تعديلات على المحاذاة والمسافة البادئة وتباعد الأسطر والعناصر الأسلوبية الأخرى لتحسين مظهر المحتوى وقابليته للقراءة.

#### س: هل يمكنني تطبيق تنسيقات مختلفة على فقرات مختلفة في نفس المستند؟

 ج: نعم ، يمكنك تطبيق تنسيقات مختلفة على فقرات مختلفة داخل نفس المستند. باستخدام ملف`ParagraphFormat` الكائن وتعديل خصائصه ، يمكنك تخصيص مظهر كل فقرة بشكل مستقل.

#### س: هل يدعم Aspose.Words for .NET خيارات تنسيق النص الأخرى؟

ج: نعم ، تقدم Aspose.Words for .NET دعمًا شاملاً لتنسيق النص. يتضمن ميزات لتعديل أنماط الخطوط والأحجام والألوان والعديد من سمات النص الأخرى. يمكنك تحسين التمثيل المرئي للنص في مستندات Word برمجيًا.

#### س: هل يتوافق Aspose.Words for .NET مع تنسيقات المستندات الأخرى؟

ج: نعم ، يدعم Aspose.Words for .NET تنسيقات مستندات متنوعة ، بما في ذلك DOCX و DOC و RTF و HTML والمزيد. يوفر واجهات برمجة تطبيقات قوية للعمل مع أنواع مختلفة من المستندات ، مما يسمح لك بتحويل المستندات ومعالجتها وإنشاءها بكفاءة.