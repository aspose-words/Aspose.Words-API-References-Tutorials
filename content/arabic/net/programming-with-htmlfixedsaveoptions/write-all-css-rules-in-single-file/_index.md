---
title: كتابة جميع قواعد Css في ملف واحد
linktitle: كتابة جميع قواعد Css في ملف واحد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

عند تحويل مستند Word إلى HTML ثابت في تطبيق C#، قد ترغب في دمج جميع قواعد CSS في ملف واحد لتحسين التنظيم وسهولة النقل. باستخدام مكتبة Aspose.Words لـ .NET، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات الحفظ HtmlFixedSaveOptions. في هذا الدليل خطوة بخطوة، سنرشدك خلال كيفية استخدام Aspose.Words for .NET C# كود المصدر لتحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام خيارات الحفظ HtmlFixedSaveOptions.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في منصات مختلفة بما في ذلك .NET. فهو يوفر العديد من الميزات لمعالجة المستندات، مثل إدراج النص وتغيير التنسيق وإضافة الأقسام وغير ذلك الكثير.

## تحميل مستند الوورد

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى HTML ثابت. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

في هذا المثال، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى HTML ثابت. استخدم فئة HtmlFixedSaveOptions وقم بتعيين الخاصية SaveFontFaceCssSeparately على false لكتابة كافة قواعد CSS في ملف واحد. هيريس كيفية القيام بذلك:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

نقوم بإنشاء كائن HtmlFixedSaveOptions جديد ونقوم بتعيين الخاصية SaveFontFaceCssSeparately على false لكتابة جميع قواعد CSS في ملف واحد.

## إصلاح تحويل مستند HTML

الآن بعد أن قمنا بتكوين خيارات الحفظ، يمكننا المتابعة لتحويل المستند إلى HTML ثابت. استخدم طريقة Save الخاصة بفئة Document لحفظ المستند المحول بتنسيق HTML ثابت عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

في هذا المثال، نقوم بحفظ المستند المحول باسم "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" باستخدام خيارات الحفظ المحددة.

### مثال على التعليمات البرمجية المصدر لـ HtmlFixedSaveOptions مع ميزة "كتابة كافة قواعد CSS في ملف واحد" باستخدام Aspose.Words for .NET

```csharp
// مسار الوصول إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند الوورد
Document doc = new Document(dataDir + "Document.docx");

// قم بتكوين خيارات النسخ الاحتياطي باستخدام ميزة "كتابة كافة قواعد CSS في ملف واحد".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// تحويل المستند إلى HTML ثابت
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## خاتمة

في هذا الدليل، تناولنا كيفية تحويل مستند Word إلى HTML ثابت عن طريق كتابة جميع قواعد CSS في ملف واحد باستخدام HtmlFixedSaveOptions مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام كود مصدر C# المقدم، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C# الخاص بك. إن كتابة كافة قواعد CSS في ملف واحد يجعل من السهل تنظيم وإدارة كود HTML الذي تم إنشاؤه أثناء تحويل المستند.