---
title: استخدم الخط من الجهاز المستهدف
linktitle: استخدم الخط من الجهاز المستهدف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز الهدف باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

عند تحويل مستند Word إلى مستند HTML ثابت في تطبيق C # ، قد ترغب في استخدام خطوط الجهاز الهدف لضمان احتفاظ HTML بالشكل والنمط الأصلي للمستند. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات حفظ HtmlFixedSaveOptions. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لتحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز الهدف باستخدام HtmlFixedSaveOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تحميل مستند Word

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى HTML ثابت. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

في هذا المثال ، نقوم بتحميل المستند "Bullet Points with Alternative font.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى HTML ثابت. استخدم فئة HtmlFixedSaveOptions وقم بتعيين الخاصية UseTargetMachineFonts على true لتخبر Aspose.Words باستخدام الخطوط من الجهاز الهدف. هيريس كيفية القيام بذلك:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

نقوم بإنشاء كائن HtmlFixedSaveOptions جديد وقمنا بتعيين الخاصية UseTargetMachineFonts على true لاستخدام خطوط الجهاز الهدف عند التحويل.

## ثابت تحويل مستند HTML

الآن بعد أن قمنا بتكوين خيارات الحفظ ، يمكننا المتابعة لتحويل المستند إلى HTML ثابت. استخدم طريقة Save لفئة Document لحفظ المستند المحول بتنسيق HTML ثابت عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

في هذا المثال ، نحفظ المستند المحول باسم "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" باستخدام خيارات الحفظ المحددة.

### مثال على شفرة المصدر لـ HtmlFixedSaveOptions مع ميزة "استخدام الخطوط من الجهاز الهدف" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل مستند Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// تكوين خيارات النسخ الاحتياطي باستخدام ميزة "استخدام الخطوط من الجهاز الهدف"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// تحويل المستند إلى HTML ثابت
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## خاتمة

في هذا الدليل ، شرحنا كيفية تحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز الهدف مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يضمن التحويل إلى HTML ثابت مع خطوط الجهاز الهدف عرضًا أمينًا ومتسقًا للمستند بتنسيق HTML.
