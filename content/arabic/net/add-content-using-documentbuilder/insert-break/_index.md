---
title: إدراج فاصل في مستند Word
linktitle: إدراج فاصل في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج فواصل الصفحات في مستندات Word باستخدام Aspose.Words لـ .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-break/
---
في هذا المثال الشامل، ستتعلم كيفية إدراج فواصل الصفحات في مستند Word باستخدام أسلوب InsertBreak في Aspose.Words لـ .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من التحكم في فواصل الصفحات داخل المستند الخاص بك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد وDocumentBuilder
للبدء، قم بإنشاء مستند جديد باستخدام فئة Document وقم بتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج المحتوى وفواصل الصفحات
بعد ذلك، استخدم طريقة Writeln لفئة DocumentBuilder لإضافة محتوى إلى المستند. لإدراج فاصل صفحات، استخدم الأسلوب InsertBreak مع المعلمة BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## الخطوة 3: احفظ المستند
بعد إدراج المحتوى وفواصل الصفحات، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### مثال على التعليمات البرمجية المصدر لإدراج فاصل باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدراج فواصل الصفحات باستخدام Aspose.Words لـ .NET:

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

تذكر تعديل الكود وفقًا لمتطلباتك المحددة وتعزيزه بوظائف إضافية حسب الحاجة.


## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج فواصل الصفحات في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن التحكم في ترقيم الصفحات وتخطيط مستندك عن طريق إدراج فواصل الصفحات في المواضع المطلوبة.

### الأسئلة الشائعة

#### س: هل يمكنني إدراج أنواع مختلفة من الفواصل إلى جانب فواصل الصفحات؟

ج: بالتأكيد! يدعم Aspose.Words for .NET أنواعًا مختلفة من الفواصل، بما في ذلك فواصل الصفحات وفواصل الأعمدة وفواصل الأقسام. يمكنك استخدام الأسلوب InsertBreak مع معلمات BreakType مختلفة لإدراج نوع الفاصل المطلوب.

#### س: هل يمكنني إدراج فواصل صفحات في أقسام معينة من المستند؟

ج: نعم، يمكنك إدراج فواصل الصفحات في مواقع محددة داخل المستند. باستخدام DocumentBuilder، يمكنك التحكم في موضع فواصل الصفحات استنادًا إلى محتوى المستند وبنيته.

#### س: هل سيتم الاحتفاظ بفواصل الصفحات عند حفظ المستند بتنسيقات ملفات مختلفة؟

ج: نعم، يتم الاحتفاظ بفواصل الصفحات المُدرجة باستخدام Aspose.Words لـ .NET عند حفظ المستند بتنسيقات ملفات مختلفة، مثل DOCX أو PDF أو RTF. وهذا يضمن ترقيم الصفحات والتخطيط المتسق عبر تنسيقات الملفات المختلفة.

#### س: هل يمكنني تخصيص مظهر فواصل الصفحات؟

ج: فواصل الصفحات غير مرئية في المستند نفسه، ولكن يمكنك ضبط تنسيق المحتوى وتخطيطه قبل فواصل الصفحات وبعدها للتحكم في مظهر المستند.

#### س: هل Aspose.Words for .NET مناسب لكل من تطبيقات سطح المكتب والويب؟

ج: نعم، Aspose.Words for .NET عبارة عن مكتبة متعددة الاستخدامات ومناسبة لكل من تطبيقات سطح المكتب والويب. سواء كنت تقوم بإنشاء تطبيق Windows أو نظام قائم على الويب، يمكنك دمج المكتبة دون عناء.