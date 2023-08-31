---
title: استخدم الخط من الجهاز المستهدف
linktitle: استخدم الخط من الجهاز المستهدف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز المستهدف باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

عند تحويل مستند Word إلى HTML ثابت في تطبيق C#، قد ترغب في استخدام خطوط الجهاز المستهدف للتأكد من احتفاظ HTML المعروض بالشكل والنمط الأصليين للمستند. باستخدام مكتبة Aspose.Words لـ .NET، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات الحفظ HtmlFixedSaveOptions. في هذا الدليل خطوة بخطوة، سنرشدك عبر كيفية استخدام التعليمات البرمجية المصدر لـ C# الخاصة بـ Aspose.Words لـ .NET لتحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز المستهدف باستخدام HtmlFixedSaveOptions.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في منصات مختلفة بما في ذلك .NET. فهو يوفر العديد من الميزات لمعالجة المستندات، مثل إدراج النص وتغيير التنسيق وإضافة الأقسام وغير ذلك الكثير.

## تحميل مستند الوورد

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى HTML ثابت. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

في هذا المثال، نقوم بتحميل المستند "Bullet Points with Alternative Font.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى HTML ثابت. استخدم فئة HtmlFixedSaveOptions وقم بتعيين خاصية UseTargetMachineFonts على القيمة true لإخبار Aspose.Words باستخدام الخطوط من الجهاز الهدف. هيريس كيفية القيام بذلك:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

نقوم بإنشاء كائن HtmlFixedSaveOptions جديد ونقوم بتعيين خاصية UseTargetMachineFonts على القيمة true لاستخدام خطوط الجهاز المستهدف عند التحويل.

## إصلاح تحويل مستند HTML

الآن بعد أن قمنا بتكوين خيارات الحفظ، يمكننا المتابعة لتحويل المستند إلى HTML ثابت. استخدم طريقة Save الخاصة بفئة Document لحفظ المستند المحول بتنسيق HTML ثابت عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

في هذا المثال، نقوم بحفظ المستند المحول باسم "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" باستخدام خيارات الحفظ المحددة.

### مثال على التعليمات البرمجية المصدر لـ HtmlFixedSaveOptions مع ميزة "استخدام الخطوط من الجهاز المستهدف" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند الوورد
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//قم بتكوين خيارات النسخ الاحتياطي باستخدام ميزة "استخدام الخطوط من الجهاز المستهدف".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// تحويل المستند إلى HTML ثابت
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## خاتمة

في هذا الدليل، شرحنا كيفية تحويل مستند Word إلى HTML ثابت باستخدام خطوط الجهاز المستهدف مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام كود مصدر C# المقدم، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C# الخاص بك. يضمن التحويل إلى HTML ثابت باستخدام خطوط الجهاز المستهدف عرضًا صادقًا ومتسقًا للمستند بتنسيق HTML.
