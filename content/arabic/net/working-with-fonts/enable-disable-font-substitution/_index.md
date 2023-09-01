---
title: تمكين تعطيل استبدال الخط
linktitle: تمكين تعطيل استبدال الخط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية تمكين أو تعطيل استبدال الخطوط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/enable-disable-font-substitution/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تمكين أو تعطيل استبدال الخطوط في مستند Word عند عرضه باستخدام مكتبة Aspose.Words لـ .NET. يتيح لك تمكين أو تعطيل استبدال الخطوط التحكم فيما إذا كان سيتم استبدال الخطوط المفقودة تلقائيًا بخط افتراضي أم لا. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك
- مستند Word الذي تريد عرضه مع استبدال الخط أو بدونه

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتكوين إعدادات الخط
 بعد ذلك، سنقوم بتحميل مستند Word الذي تريد عرضه وإنشاء مثيل لـ`FontSettings` فئة للتعامل مع إعدادات الخط. سنقوم بتعيين تجاوز الخط الافتراضي عن طريق تحديد اسم الخط`DefaultFontName` وتعطيل تجاوز معلومات الخط باستخدام`Enabled` ضبط ل`false`.

```csharp
// قم بتحميل المستند
Document doc = new Document(dataDir + "Rendering.docx");

// تكوين إعدادات الخط
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// قم بتطبيق إعدادات الخط على المستند
doc.FontSettings = fontSettings;
```

## الخطوة 3: احفظ المستند المقدم
أخيرًا، سنقوم بحفظ المستند المقدم، والذي سيحترم إعدادات تجاوز الخط المحددة.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### نموذج التعليمات البرمجية المصدر لـ Enable Disable Font Substitution باستخدام Aspose.Words لـ .NET 

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## خاتمة
في هذا البرنامج التعليمي، رأينا كيفية تمكين أو تعطيل استبدال الخط في مستند Word عند عرضه باستخدام Aspose.Words for .NET. من خلال التحكم في استبدال الخطوط، يمكنك التأثير على كيفية معالجة الخطوط المفقودة في المستندات المقدمة. لا تتردد في استخدام هذه الميزة لتخصيص إدارة الخطوط في مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س: كيف يمكنني تمكين استبدال الخط في مستند Word باستخدام Aspose.Words؟

ج: لتمكين استبدال الخطوط في مستند Word باستخدام Aspose.Words، يمكنك استخدام واجهة برمجة التطبيقات (API) لتحديد الخطوط البديلة لاستخدامها عند عدم توفر الخطوط المطلوبة. سيضمن هذا تصورًا متسقًا للنص، حتى بدون الخطوط الأصلية.

#### س: هل من الممكن تعطيل استبدال الخط في مستند Word باستخدام Aspose.Words؟

ج: نعم، باستخدام Aspose.Words، يمكنك تعطيل استبدال الخطوط في مستند Word. باستخدام واجهة برمجة التطبيقات (API)، يمكنك منع Word من استبدال الخطوط المطلوبة بخطوط أخرى، مما يحافظ على المظهر الأصلي للنص.

#### س: ماذا يحدث عندما تكون الخطوط المطلوبة مفقودة أثناء الاستبدال في مستند Word؟

ج: عندما تكون الخطوط المطلوبة مفقودة أثناء الاستبدال في مستند Word، يمكن لـ Aspose.Words اكتشاف هذه المشكلة وتزويدك بخيارات لإصلاحها. يمكنك اختيار استبدال الخطوط المفقودة بخطوط بديلة أو تضمين الخطوط المفقودة في المستند، مما يضمن العرض الصحيح.

#### س: كيف يمكنني التعامل مع الخطوط المفقودة عند استبدال مستند Word باستخدام Aspose.Words؟

ج: للتعامل مع الخطوط المفقودة عند الاستبدال في مستند Word باستخدام Aspose.Words، يمكنك استخدام واجهة برمجة التطبيقات (API) لاكتشاف الخطوط المفقودة وتوفير خيارات الدقة. يمكنك اختيار استبدال الخطوط المفقودة بخطوط بديلة أو تضمين الخطوط المفقودة في المستند، حسب احتياجاتك.

#### س: هل من المهم التحكم في استبدال الخط في مستند Word؟

ج: نعم، من المهم التحكم في استبدال الخط في مستند Word للحفاظ على التكامل البصري للنص. باستخدام Aspose.Words لتمكين أو تعطيل استبدال الخطوط، يمكنك التأكد من استخدام الخطوط المطلوبة وتجنب المشكلات المتعلقة بالخطوط المفقودة أو المستبدلة.