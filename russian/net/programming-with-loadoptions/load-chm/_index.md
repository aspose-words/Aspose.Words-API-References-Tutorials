---
title: تحميل Chm
linktitle: تحميل Chm
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحميل ملفات CHM باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-loadoptions/load-chm/
---

عند العمل باستخدام ملفات تعليمات HTML (CHM) في تطبيق C # ، من المهم أن تكون قادرًا على تحميلها بشكل صحيح. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحميل ملفات CHM باستخدام خيارات التحميل المناسبة. في هذا الدليل التفصيلي ، سنوضح لك كيفية استخدام Aspose.Words للكود المصدري .NET C # لتحميل ملف CHM باستخدام خيارات تحميل LoadOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تكوين خيارات التحميل

الخطوة الأولى هي تكوين خيارات التحميل لملف CHM الخاص بنا. استخدم فئة LoadOptions لتحديد معلمات التحميل. في حالتنا ، نحتاج إلى ضبط خاصية التشفير على الترميز المناسب لملفات CHM ، عادةً "windows-1251". هيريس كيفية القيام بذلك:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

قمنا بإنشاء كائن LoadOptions جديد وقمنا بتعيين خاصية التشفير على ترميز "windows-1251" لملفات CHM.

## تحميل ملف CHM

الآن بعد أن قمنا بتكوين خيارات التحميل ، يمكننا تحميل ملف CHM باستخدام فئة المستند وتحديد خيارات التحميل. هنا مثال :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

في هذا المثال ، نقوم بتحميل ملف CHM "HTML help.chm" الموجود في دليل المستندات باستخدام خيارات التحميل المحددة.

### مثال على شفرة المصدر لـ LoadOptions مع وظيفة "Load Chm" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// تكوين خيارات التحميل مع ميزة "تحميل Chm"
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// قم بتحميل ملف CHM بالخيارات المحددة
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## خاتمة

في هذا الدليل ، شرحنا كيفية تحميل ملف CHM باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يعد تحميل ملفات CHM بشكل صحيح أمرًا ضروريًا لتتمكن من معالجتها وتحويلها بكفاءة باستخدام Aspose.Words.