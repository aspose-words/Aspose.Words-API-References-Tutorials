---
title: تحميل قاموس الواصلة للغة
linktitle: تحميل قاموس الواصلة للغة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من[Aspose.Releases] https://releases.aspose.com/words/net/.

## الخطوة 1: تحميل المستند

أولاً ، قم بتحميل المستند الخاص بك من الدليل المحدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## الخطوة 2: تحميل قاموس الواصلة

بعد ذلك ، افتح دفقًا إلى ملف قاموس الواصلة واحفظه للغة المطلوبة. في هذا المثال ، نقوم بتحميل قاموس للألمانية السويسرية (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

تأكد من أن لديك ملف القاموس المناسب في دليل البيانات الخاص بك.

## الخطوة 3: احفظ المستند المعدل

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

لذا ! لقد نجحت في تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET.

### مثال على شفرة المصدر لتحميل قاموس الواصلة للغة باستخدام Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.

### التعليمات

#### س: كيف يتم تحميل قاموس لفظي للغة معينة في Aspose.Words؟

 ج: لتحميل قاموس مقطعي للغة معينة في Aspose. Words ، يمكنك استخدام`Hyphenation` الطبقة و`LoadDictionary()` طريقة. قم بإنشاء مثيل لـ`Hyphenation` الطبقة واستدعاء`LoadDictionary()` طريقة تحديد المسار إلى ملف قاموس المقطع للغة المطلوبة. سيؤدي هذا إلى تحميل قاموس المقطع الصوتي إلى Aspose.Words.

#### س: أين يمكنني العثور على ملفات قاموس التنصيص للغات مختلفة؟

ج: يمكنك العثور على ملفات قاموس التنصيص للغات مختلفة على موارد متنوعة عبر الإنترنت. عادة ما تكون هذه الملفات بتنسيق XML أو TEX. يمكنك العثور على قواميس مقطعية مفتوحة المصدر للغات مختلفة على مواقع الويب المخصصة لمشاريع اللغويات أو مستودعات الكود المصدري.

#### س: كيف يمكنني تطبيق القاموس المقطعي المحمل على مستند في Aspose.Words؟

 ج: لتطبيق قاموس المقطع المحمل على مستند في Aspose. الكلمات ، تحتاج إلى تكرار الكلمات الموجودة في المستند واستخدام`Hyphenate()` طريقة`Hyphenation` الفصل للحصول على مقاطع الكلمات. يمكنك بعد ذلك تنسيق الكلمات المقطوعة حسب الحاجة ، على سبيل المثال عن طريق إضافة واصلات بين المقاطع.

#### س: ما هي اللغات المدعومة للمقاطع الصوتية في Aspose.Words؟

ج: يدعم Aspose.Words تقسيم عدة لغات بما في ذلك الإنجليزية والفرنسية والإسبانية والألمانية والإيطالية والهولندية والروسية والبرتغالية والسويدية والنرويجية والدنماركية والفنلندية والبولندية والتشيكية وغيرها الكثير. تحقق من وثائق Aspose.Words للحصول على قائمة كاملة باللغات المدعومة للمقاطع.