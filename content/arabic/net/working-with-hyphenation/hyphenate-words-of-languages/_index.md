---
title: الواصلة الكلمات من اللغات
linktitle: الواصلة الكلمات من اللغات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية وصل الكلمات بلغات مختلفة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-hyphenation/hyphenate-words-of-languages/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية وصل الكلمات بلغات مختلفة في مستندات Word باستخدام Aspose.Words for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء، تأكد من تثبيت Aspose.Words for .NET وتكوينه في بيئة التطوير لديك. إذا لم تقم بذلك بالفعل، قم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً، قم بتهيئة`Document` الكائن عن طريق تحديد المسار إلى مستندك المصدر الذي يحتوي على نص بلغات مختلفة:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## الخطوة 2: حفظ قواميس الواصلة

بعد ذلك، قم بحفظ قواميس الواصلة للغات المختلفة التي تريد معالجتها. في هذا المثال، نقوم بتسجيل قواميس اللغة الإنجليزية الأمريكية والألمانية السويسرية:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

تأكد من أن لديك ملفات القاموس المناسبة في دليل البيانات الخاص بك.

## الخطوة 3: معالجة الكلمات بالواصلة

 يمكنك الآن استخدام ميزات الواصلة لمعالجة الكلمات بلغات مختلفة. يمكنك استخدام أساليب مختلفة`Document` أو`DocumentBuilder` اعتمادا على احتياجاتك المحددة.

```csharp
// مثال: استخدام طريقة الواصلة في DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## الخطوة 4: احفظ المستند

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

لذا ! لقد نجحت في معالجة الكلمات عن طريق وصلها بلغات مختلفة في مستند Word باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لواصلة الكلمات باستخدام Aspose.Words لـ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.

### الأسئلة الشائعة

#### س: كيف يمكنني تقسيم كلمة إلى مقطع لفظي بلغة معينة باستخدام Aspose.Words؟

 ج: لتقسيم كلمة إلى مقطع لفظي في لغة معينة باستخدام Aspose.Words، يمكنك استخدام`Hyphenation` الطبقة و`Hyphenate()` طريقة. إنشاء مثيل لـ`Hyphenation` فئة تحدد اللغة المطلوبة، ثم اتصل بـ`Hyphenate()` طريقة تمرير الكلمة إلى مقطع كوسيطة. سيعطيك هذا مقاطع الكلمة باللغة المحددة.

#### س: ما هي رموز اللغة التي يجب أن أستخدمها لتحديد لغة المقطع في Aspose.Words؟

ج: لتحديد لغة المقطع في Aspose.Words، يجب عليك استخدام رموز اللغة المناسبة. على سبيل المثال، يمكنك استخدام "en" للغة الإنجليزية، و"fr" للغة الفرنسية، و"es" للغة الإسبانية، و"de" للغة الألمانية، وما إلى ذلك. راجع وثائق Aspose.Words للحصول على قائمة كاملة برموز اللغات المدعومة.

#### س: هل يعمل المقطع لجميع اللغات في Aspose.Words؟

ج: يعتمد المقطع في Aspose.Words على قواعد المقطع الخاصة باللغة. على الرغم من أن Aspose.Words يدعم نطاقًا واسعًا من اللغات، إلا أن بعض اللغات قد لا تكون مدعومة أو قد لا يكون التصنيف المقطعي متاحًا لها. راجع وثائق Aspose.Words لمعرفة اللغات المدعومة للتقسيم المقطعي.