---
title: تحديد الخط الافتراضي عند العرض
linktitle: تحديد الخط الافتراضي عند العرض
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحديد الخط الافتراضي عند عرض مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/specify-default-font-when-rendering/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتحديد الخط الافتراضي عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي، ستعرف كيفية تحديد خط افتراضي لاستخدامه عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند لعرضه
 بعد ذلك، تحتاج إلى تحميل المستند لعرضه باستخدام ملف`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تعيين الخط الافتراضي
 يمكنك الآن تحديد الخط الافتراضي الذي سيتم استخدامه عند العرض عن طريق إنشاء مثيل لـ`FontSettings` الصف وتحديد`DefaultFontName` ملكية`DefaultFontSubstitution` يعترض على`DefaultFontSubstitution` هدف`SubstitutionSettings` ل`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## الخطوة 4: احفظ المستند المقدم
 وأخيرًا، يمكنك حفظ المستند الذي تم عرضه في ملف باستخدام الملف`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### نموذج التعليمات البرمجية المصدر لتحديد الخط الافتراضي عند العرض باستخدام Aspose.Words لـ .NET 

```csharp
//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// إذا لم يتم العثور على الخط الافتراضي المحدد هنا أثناء العرض، فعندئذٍ
// يتم استخدام الخط الأقرب على الجهاز بدلاً من ذلك.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحديد الخط الافتراضي عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة، يمكنك بسهولة تعيين خط افتراضي لاستخدامه عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام الخطوط الموجودة في مستنداتك. ومن خلال هذه المعرفة، يمكنك التحكم في عرض مستنداتك وتخصيصها وفقًا لاحتياجاتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني تحديد خط افتراضي عند التحويل إلى PDF في Aspose.Words؟

 ج: لتحديد خط افتراضي عند التحويل إلى PDF في Aspose.Words، يمكنك استخدام`PdfOptions`فئة وتعيين`DefaultFontName` خاصية اسم الخط المطلوب.

#### س: ماذا لو لم يكن الخط الافتراضي متاحًا عند التحويل إلى PDF؟

ج: إذا لم يكن الخط الافتراضي المحدد متاحًا عند التحويل إلى PDF، فسيستخدم Aspose.Words خطًا بديلاً لعرض النص في المستند المحول. قد يتسبب هذا في اختلاف طفيف في المظهر عن الخط الأصلي.

#### س: هل يمكنني تحديد خط افتراضي لتنسيقات الإخراج الأخرى، مثل DOCX أو HTML؟

ج: نعم، يمكنك تحديد خط افتراضي لتنسيقات الإخراج الأخرى مثل DOCX أو HTML باستخدام خيارات التحويل المناسبة وتعيين الخاصية المقابلة لكل تنسيق.

#### س: كيف يمكنني التحقق من الخط الافتراضي المحدد في Aspose.Words؟

 ج: للتحقق من الخط الافتراضي المحدد في Aspose.Words، يمكنك استخدام`DefaultFontName` ملكية`PdfOptions` class واسترجاع اسم الخط الذي تم تكوينه.

#### س: هل من الممكن تحديد خط افتراضي مختلف لكل قسم من المستند؟

ج: نعم، من الممكن تحديد خط افتراضي مختلف لكل قسم من المستند باستخدام خيارات التنسيق الخاصة بكل قسم. ومع ذلك، قد يتطلب هذا معالجة أكثر تقدمًا للمستند باستخدام ميزات Aspose.Words.