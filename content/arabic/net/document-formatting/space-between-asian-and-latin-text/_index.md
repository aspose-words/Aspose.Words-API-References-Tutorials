---
title: المسافة بين النص الآسيوي واللاتيني في مستند Word
linktitle: المسافة بين النص الآسيوي واللاتيني في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضبط المسافة تلقائيًا بين النص الآسيوي والنص اللاتيني في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/space-between-asian-and-latin-text/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية استخدام ميزة المسافة بين النص الآسيوي والنص اللاتيني في ميزة مستند Word باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء، قم بإنشاء مستند جديد وكائن DocumentBuilder مرتبط. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إعداد المسافة بين النص الآسيوي واللاتيني

سنقوم الآن بتكوين المسافة بين النص الآسيوي والنص اللاتيني باستخدام خصائص كائن ParagraphFormat. إليك الطريقة:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### مثال على التعليمات البرمجية المصدر للمسافة بين النص الآسيوي واللاتيني باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة المسافة بين النص الآسيوي واللاتيني باستخدام Aspose.Words لـ .NET:


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

باستخدام هذا الرمز، ستتمكن تلقائيًا من ضبط المسافة بين النص الآسيوي والنص اللاتيني في مستندك باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي، استكشفنا عملية استخدام ميزة المسافة لضبط التباعد بين النص الآسيوي والنص اللاتيني في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الخطوات الموضحة، يمكنك ضمان التباعد والمحاذاة المناسبة، وهو أمر مفيد بشكل خاص عند التعامل مع المحتوى الآسيوي واللاتيني المختلط.

### الأسئلة الشائعة

#### س: ما هي ميزة المسافة بين النص الآسيوي واللاتيني في مستند Word؟

ج: تشير ميزة المسافة بين النص الآسيوي والنص اللاتيني في مستند Word إلى القدرة على ضبط التباعد تلقائيًا بين النص المكتوب بنصوص مختلفة، مثل اللغة الآسيوية (على سبيل المثال، الصينية واليابانية) واللاتينية (على سبيل المثال، الإنجليزية).

#### س: ما سبب أهمية ضبط المسافة بين النص الآسيوي والنص اللاتيني؟

ج: يعد ضبط المسافة بين النص الآسيوي والنص اللاتيني أمرًا ضروريًا لضمان تناغم النصوص المختلفة داخل المستند. يعمل التباعد المناسب على تحسين إمكانية القراءة والمظهر المرئي العام، مما يمنع النص من الظهور بشكل ضيق جدًا أو منتشر.

#### س: هل يمكنني تخصيص تعديلات المسافة بين البرامج النصية المختلفة؟

 ج: نعم، يمكنك تخصيص تعديلات المسافة بين البرامج النصية المختلفة باستخدام`AddSpaceBetweenFarEastAndAlpha` و`AddSpaceBetweenFarEastAndDigit` ملكيات. من خلال تمكين هذه الخصائص أو تعطيلها، يمكنك التحكم في المسافة بين النص الآسيوي والنص اللاتيني، وكذلك بين النص الآسيوي والأرقام.

#### س: هل يدعم Aspose.Words for .NET ميزات تنسيق المستندات الأخرى؟

ج: نعم، يوفر Aspose.Words for .NET دعمًا شاملاً لمختلف ميزات تنسيق المستندات. يتضمن وظائف لأنماط الخطوط والفقرات والجداول والصور والمزيد. يمكنك التعامل مع مستندات Word الخاصة بك وتنسيقها بشكل فعال برمجياً.

#### س: أين يمكنني العثور على موارد ووثائق إضافية لـ Aspose.Words لـ .NET؟

 ج: للحصول على موارد ووثائق شاملة حول استخدام Aspose.Words for .NET، تفضل بزيارة[مرجع Aspose.Words API](https://reference.aspose.com/words/net/). ستجد هناك أدلة تفصيلية، وبرامج تعليمية، وأمثلة للتعليمات البرمجية، ومراجع واجهة برمجة التطبيقات (API) لمساعدتك على الاستفادة بشكل فعال من الميزات القوية لـ Aspose.Words for .NET.