---
title: المسافة بين النص الآسيوي واللاتيني في مستند Word
linktitle: المسافة بين النص الآسيوي واللاتيني في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية ضبط المسافة تلقائيًا بين النص الآسيوي واللاتيني في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/space-between-asian-and-latin-text/
---
في هذا البرنامج التعليمي ، سوف نوضح لك كيفية استخدام ميزة المسافة بين النص الآسيوي واللاتيني في ميزة مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إعداد المسافة بين النص الآسيوي واللاتيني

سنقوم الآن بتكوين المسافة بين النص الآسيوي واللاتيني باستخدام خصائص الكائن ParagraphFormat. إليك الطريقة:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### مثال على شفرة المصدر للمسافة بين النص الآسيوي واللاتيني باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة المسافة بين النص الآسيوي واللاتيني مع Aspose.Words for .NET:


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

باستخدام هذا الرمز ، ستتمكن من ضبط المسافة تلقائيًا بين النص الآسيوي واللاتيني في المستند باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا عملية استخدام ميزة Space لضبط التباعد بين النص الآسيوي والنص اللاتيني في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك ضمان تباعد ومحاذاة مناسبتين ، خاصة عند التعامل مع محتوى آسيوي ولاتيني مختلط.

### التعليمات

#### س: ما هي ميزة المسافة بين النص الآسيوي واللاتيني في مستند Word؟

ج: تشير ميزة المسافة بين النص الآسيوي واللاتيني في مستند Word إلى القدرة على ضبط التباعد تلقائيًا بين النص المكتوب بنصوص مختلفة ، مثل الآسيوية (على سبيل المثال ، الصينية ، اليابانية) واللاتينية (على سبيل المثال ، الإنجليزية).

#### س: لماذا يعد ضبط المسافة بين النص الآسيوي والنص اللاتيني أمرًا مهمًا؟

ج: يعد ضبط المسافة بين النص الآسيوي واللاتيني أمرًا بالغ الأهمية لضمان دمج النصوص المختلفة بشكل متناغم داخل المستند. تعمل التباعد المناسب على تحسين إمكانية القراءة والمظهر المرئي العام ، مما يمنع النص من الظهور بشكل ضيق للغاية أو منتشر.

#### س: هل يمكنني تخصيص تعديلات المسافة بين النصوص المختلفة؟

 ج: نعم ، يمكنك تخصيص تعديلات المسافة بين البرامج النصية المختلفة باستخدام`AddSpaceBetweenFarEastAndAlpha` و`AddSpaceBetweenFarEastAndDigit` ملكيات. من خلال تمكين هذه الخصائص أو تعطيلها ، يمكنك التحكم في المسافة بين النص الآسيوي واللاتيني ، وكذلك بين النصوص والأرقام الآسيوية.

#### س: هل يدعم Aspose.Words for .NET ميزات تنسيق المستندات الأخرى؟

ج: نعم ، يوفر Aspose.Words for .NET دعمًا شاملاً للعديد من ميزات تنسيق المستندات. يتضمن وظائف لأنماط الخطوط والفقرات والجداول والصور والمزيد. يمكنك معالجة مستندات Word وتنسيقها بشكل فعال برمجيًا.

#### س: أين يمكنني العثور على موارد ووثائق إضافية لـ Aspose.Words for .NET؟

 ج: للحصول على موارد ووثائق شاملة حول استخدام Aspose.Words for .NET ، قم بزيارة[مرجع Aspose.Words API](https://reference.aspose.com/words/net/). هناك ، ستجد أدلة تفصيلية ، ودروس ، وأمثلة على التعليمات البرمجية ، ومراجع API لمساعدتك على الاستفادة الفعالة من الميزات القوية لـ Aspose.Words for .NET.