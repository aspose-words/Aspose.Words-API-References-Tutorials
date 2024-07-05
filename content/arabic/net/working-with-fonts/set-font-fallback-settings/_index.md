---
title: ضبط إعدادات الخط الاحتياطي
linktitle: ضبط إعدادات الخط الاحتياطي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إعداد إعدادات الخط الاحتياطي في Aspose.Words لـ .NET. يضمن هذا الدليل الشامل عرض جميع الأحرف في مستنداتك بشكل صحيح.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-font-fallback-settings/
---

عند العمل مع المستندات التي تحتوي على عناصر نصية متنوعة، مثل لغات مختلفة أو أحرف خاصة، فمن الضروري التأكد من عرض هذه العناصر بشكل صحيح. يوفر Aspose.Words for .NET ميزة قوية تسمى Font Fallback Settings، والتي تساعد في تحديد قواعد استبدال الخطوط عندما لا يدعم الخط الأصلي أحرفًا معينة. في هذا الدليل، سنستكشف كيفية إعداد إعدادات الخط الاحتياطي باستخدام Aspose.Words لـ .NET في برنامج تعليمي خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# وإطار عمل .NET.
-  Aspose.Words لـ .NET: قم بالتنزيل والتثبيت من[رابط التحميل](https://releases.aspose.com/words/net/).
- بيئة التطوير: إعداد مثل Visual Studio لكتابة وتشغيل التعليمات البرمجية الخاصة بك.
-  نموذج مستند: احصل على نموذج مستند (على سبيل المثال،`Rendering.docx`) جاهز للاختبار.
- قواعد الخط الاحتياطية XML: قم بإعداد ملف XML يحدد القواعد الاحتياطية للخط.

## استيراد مساحات الأسماء

لاستخدام Aspose.Words، تحتاج إلى استيراد مساحات الأسماء الضرورية. يتيح ذلك الوصول إلى الفئات والأساليب المختلفة المطلوبة لمعالجة المستندات.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## الخطوة 1: تحديد دليل المستندات

أولاً، قم بتحديد الدليل الذي تم تخزين المستند الخاص بك فيه. يعد هذا أمرًا ضروريًا لتحديد موقع المستند ومعالجته.

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

 قم بتحميل المستند الخاص بك إلى Aspose.Words`Document` هدف. تتيح لك هذه الخطوة العمل مع المستند برمجياً.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين إعدادات الخط

 إنشاء جديد`FontSettings` كائن وتحميل الإعدادات الاحتياطية للخط من ملف XML. يحتوي ملف XML هذا على قواعد احتياطية للخط.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## الخطوة 4: تطبيق إعدادات الخط على المستند

 تعيين تكوينه`FontSettings` إلى الوثيقة. وهذا يضمن تطبيق القواعد الاحتياطية للخط عند عرض المستند.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 5: احفظ المستند

وأخيراً، احفظ المستند. سيتم استخدام إعدادات الخط الاحتياطية أثناء عملية الحفظ لضمان استبدال الخط بشكل صحيح.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## ملف XML: القواعد الاحتياطية للخط

فيما يلي مثال لكيفية ظهور ملف XML الذي يحدد القواعد الاحتياطية للخط:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## خاتمة

باتباع هذه الخطوات، يمكنك إعداد واستخدام إعدادات الخط الاحتياطي بشكل فعال في Aspose.Words لـ .NET. وهذا يضمن أن تعرض مستنداتك جميع الأحرف بشكل صحيح، حتى إذا كان الخط الأصلي لا يدعم أحرفًا معينة. سيؤدي تنفيذ هذه الإعدادات إلى تحسين جودة مستنداتك وسهولة قراءتها بشكل كبير.

## الأسئلة الشائعة

### س1: ما هو الخط الاحتياطي؟

Font Fallback هي ميزة تسمح باستبدال الخطوط عندما لا يدعم الخط الأصلي أحرفًا معينة، مما يضمن العرض المناسب لجميع عناصر النص.

### س2: هل يمكنني تحديد خطوط احتياطية متعددة؟

نعم، يمكنك تحديد خطوط احتياطية متعددة في قواعد XML. سوف يقوم Aspose.Words بفحص كل خط بالترتيب المحدد حتى يجد الخط الذي يدعم الحرف.

### س3: أين يمكنني تنزيل Aspose.Words لـ .NET؟

 يمكنك تنزيله من[صفحة التحميل Aspose](https://releases.aspose.com/words/net/).

### س4: كيف يمكنني إنشاء ملف XML لقواعد الخط الاحتياطية؟

يمكن إنشاء ملف XML باستخدام أي محرر نصوص. يجب أن يتبع الهيكل الموضح في المثال المقدم في هذا البرنامج التعليمي.

### س5: هل يتوفر دعم لـ Aspose.Words؟

 نعم، يمكنك العثور على الدعم على[منتدى دعم Aspose.Words](https://forum.aspose.com/c/words/8).