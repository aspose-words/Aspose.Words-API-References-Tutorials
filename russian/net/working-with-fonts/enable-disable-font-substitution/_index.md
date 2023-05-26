---
title: قم بتمكين تعطيل استبدال الخط
linktitle: قم بتمكين تعطيل استبدال الخط
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية تمكين أو تعطيل استبدال الخط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/enable-disable-font-substitution/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تمكين أو تعطيل استبدال الخط في مستند Word عند عرضه باستخدام مكتبة Aspose.Words لـ .NET. يتيح لك تمكين أو تعطيل استبدال الخط التحكم في ما إذا كان سيتم استبدال الخطوط المفقودة تلقائيًا بخط افتراضي. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك
- مستند Word الذي تريد عرضه باستبدال الخط أو بدونه

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند وتكوين إعدادات الخط
 بعد ذلك ، سنقوم بتحميل مستند Word الذي تريد عرضه وإنشاء مثيل لملف`FontSettings` فئة للتعامل مع إعدادات الخط. سنقوم بتعيين تجاوز الخط الافتراضي عن طريق تحديد اسم الخط في`DefaultFontName` وتعطيل تجاوز معلومات الخط بـ`Enabled` ضبط ل`false`.

```csharp
//قم بتحميل المستند
Document doc = new Document(dataDir + "Rendering.docx");

// تكوين إعدادات الخط
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// قم بتطبيق إعدادات الخط على المستند
doc.FontSettings = fontSettings;
```

## الخطوة 3: احفظ المستند المقدم
أخيرًا ، سنحفظ المستند الذي تم تقديمه ، والذي سيحترم إعدادات تجاوز الخط المحددة.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### نموذج التعليمات البرمجية المصدر لـ Enable Disable Font Substitution باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية تمكين أو تعطيل استبدال الخط في مستند Word عند عرضه باستخدام Aspose.Words for .NET. من خلال التحكم في استبدال الخط ، يمكنك التأثير على كيفية معالجة الخطوط المفقودة في المستندات المقدمة. لا تتردد في استخدام هذه الميزة لتخصيص إدارة الخطوط في مستندات Word الخاصة بك.