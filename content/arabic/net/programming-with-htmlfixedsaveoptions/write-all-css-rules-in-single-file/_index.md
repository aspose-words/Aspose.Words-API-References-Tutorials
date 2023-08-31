---
title: اكتب جميع قواعد Css في ملف واحد
linktitle: اكتب جميع قواعد Css في ملف واحد
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

عند تحويل مستند Word إلى مستند HTML ثابت في تطبيق C # ، قد ترغب في دمج جميع قواعد CSS في ملف واحد لتحسين التنظيم وقابلية النقل. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات حفظ HtmlFixedSaveOptions. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام Aspose.Words للكود المصدري .NET C # لتحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام خيارات الحفظ HtmlFixedSaveOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تحميل مستند Word

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى HTML ثابت. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

في هذا المثال ، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى HTML ثابت. استخدم فئة HtmlFixedSaveOptions وقم بتعيين الخاصية SaveFontFaceCssSeparately على false لكتابة جميع قواعد CSS في ملف واحد. هيريس كيفية القيام بذلك:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

قمنا بإنشاء كائن HtmlFixedSaveOptions جديد وقمنا بتعيين الخاصية SaveFontFaceCssSeparately إلى false لكتابة جميع قواعد CSS في ملف واحد.

## ثابت تحويل مستند HTML

الآن بعد أن قمنا بتكوين خيارات الحفظ ، يمكننا المتابعة لتحويل المستند إلى HTML ثابت. استخدم طريقة Save لفئة Document لحفظ المستند المحول بتنسيق HTML ثابت عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

في هذا المثال ، نحفظ المستند المحول باسم "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" باستخدام خيارات الحفظ المحددة.

### مثال على شفرة المصدر لـ HtmlFixedSaveOptions مع ميزة "كتابة جميع قواعد CSS في ملف واحد" باستخدام Aspose.Words for .NET

```csharp
// مسار الوصول إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند Word
Document doc = new Document(dataDir + "Document.docx");

// تكوين خيارات النسخ الاحتياطي باستخدام ميزة "كتابة جميع قواعد CSS في ملف واحد"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// تحويل المستند إلى HTML ثابت
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## خاتمة

في هذا الدليل ، قمنا بتغطية كيفية تحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام HtmlFixedSaveOptions مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. تؤدي كتابة جميع قواعد CSS في ملف واحد إلى تسهيل تنظيم وإدارة كود HTML الذي تم إنشاؤه أثناء تحويل المستند.