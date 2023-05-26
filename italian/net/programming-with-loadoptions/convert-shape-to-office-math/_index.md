---
title: تحويل الشكل إلى مكتب الرياضيات
linktitle: تحويل الشكل إلى مكتب الرياضيات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل الأشكال إلى صيغ الرياضيات في Office عند تحميل المستندات باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-loadoptions/convert-shape-to-office-math/
---

عند العمل مع المستندات التي تحتوي على أشكال رياضية في تطبيق C # ، قد تحتاج إلى تحويلها إلى صيغ الرياضيات في Office لتحسين التوافق والعرض التقديمي. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحويل الأشكال إلى صيغ الرياضيات في Office أثناء تحميل مستند. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام Aspose.Words للكود المصدري .NET C # لتحميل مستند بتحويل الأشكال إلى صيغ الرياضيات في Office باستخدام LoadOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تكوين خيارات التحميل

الخطوة الأولى هي تكوين خيارات التحميل لوثيقتنا. استخدم فئة LoadOptions لتحديد معلمات التحميل. في حالتنا ، نريد تحويل الأشكال إلى صيغ الرياضيات في Office ، لذلك نحتاج إلى تعيين الخاصية ConvertShapeToOfficeMath إلى true. هيريس كيفية القيام بذلك:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

قمنا بإنشاء كائن LoadOptions جديد وقمنا بتعيين الخاصية ConvertShapeToOfficeMath على true لتمكين تحويل الأشكال إلى صيغ الرياضيات في Office عند تحميل المستند.

## تحميل المستند مع تحويل الأشكال إلى صيغ الرياضيات في Office

الآن بعد أن قمنا بتكوين خيارات التحميل ، يمكننا تحميل المستند باستخدام فئة Document وتحديد خيارات التحميل. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

في هذا المثال ، نقوم بتحميل المستند "Office math.docx" الموجود في دليل المستندات باستخدام خيارات التحميل المحددة.

## تسجيل الوثيقة

بعد تحميل المستند بتحويل الأشكال إلى صيغ الرياضيات في Office ، يمكنك حفظه بالتنسيق المطلوب باستخدام طريقة Save لفئة Document. على سبيل المثال ، لحفظ المستند بتنسيق docx.

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

تأكد من استبدال "dataDir" بمسار الدليل إلى مستنداتك.

### مثال على كود المصدر لـ LoadOptions مع وظيفة "Convert Shape To Office Math" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// تكوين خيارات التحميل بوظيفة "تحويل الشكل"

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// قم بتحميل المستند بالخيارات المحددة
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//احفظ المستند بالتنسيق المطلوب
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## خاتمة

في هذا الدليل ، شرحنا كيفية تحميل مستند بتحويل الأشكال إلى صيغ الرياضيات في Office باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يوفر تحويل الأشكال إلى صيغ الرياضيات في Office توافقًا وعرضًا أفضل للمستندات التي تحتوي على عناصر رياضية.
