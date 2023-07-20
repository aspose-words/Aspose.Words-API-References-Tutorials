---
title: إدراج فاصل في مستند Word
linktitle: إدراج فاصل في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج فواصل الصفحات في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-break/
---
في هذا المثال الشامل ، ستتعلم كيفية إدراج فواصل الصفحات في مستند Word باستخدام طريقة InsertBreak في Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من التحكم في فواصل الصفحات داخل المستند الخاص بك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل المحتوى وفواصل الصفحات
بعد ذلك ، استخدم طريقة Writeln لفئة DocumentBuilder لإضافة محتوى إلى المستند. لإدراج فاصل صفحات ، استخدم الأسلوب InsertBreak مع المعلمة BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## الخطوة 3: احفظ المستند
بعد إدراج المحتوى وفواصل الصفحات ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### مثال على كود المصدر لإدراج استراحة باستخدام Aspose.Words for .NET
فيما يلي شفرة المصدر الكاملة لإدخال فواصل الصفحات باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.


## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج فواصل الصفحات في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن التحكم في ترقيم الصفحات وتخطيط المستند عن طريق إدراج فواصل الصفحات في المواضع المطلوبة.

### التعليمات

#### س: هل يمكنني إدراج أنواع مختلفة من الفواصل إلى جانب فواصل الصفحات؟

ج: إطلاقا! يدعم Aspose.Words for .NET أنواعًا مختلفة من الفواصل ، بما في ذلك فواصل الصفحات وفواصل الأعمدة وفواصل الأقسام. يمكنك استخدام الأسلوب InsertBreak مع معلمات BreakType مختلفة لإدراج نوع الفاصل المطلوب.

#### س: هل يمكنني إدراج فواصل صفحات في أقسام معينة من المستند؟

ج: نعم ، يمكنك إدراج فواصل صفحات في مواقع محددة داخل المستند. باستخدام DocumentBuilder ، يمكنك التحكم في موضع فواصل الصفحات بناءً على محتوى المستند وبنيته.

#### س: هل سيتم الاحتفاظ بفواصل الصفحات عند حفظ المستند بتنسيقات ملفات مختلفة؟

ج: نعم ، يتم الاحتفاظ بفواصل الصفحات التي تم إدخالها باستخدام Aspose.Words for .NET عند حفظ المستند بتنسيقات ملفات مختلفة ، مثل DOCX أو PDF أو RTF. وهذا يضمن ترقيم صفحات وتخطيط متسقين عبر تنسيقات ملفات مختلفة.

#### س: هل يمكنني تخصيص مظهر فواصل الصفحات؟

ج: لا تظهر فواصل الصفحات في المستند نفسه ، ولكن يمكنك ضبط تنسيق المحتوى وتخطيطه قبل فواصل الصفحات وبعدها للتحكم في مظهر المستند.

#### س: هل Aspose.Words for .NET مناسب لتطبيقات سطح المكتب والويب؟

ج: نعم ، Aspose.Words for .NET مكتبة متعددة الاستخدامات مناسبة لكل من تطبيقات سطح المكتب والويب. سواء كنت تقوم ببناء تطبيق Windows أو نظام مستند إلى الويب ، يمكنك دمج المكتبة دون عناء.