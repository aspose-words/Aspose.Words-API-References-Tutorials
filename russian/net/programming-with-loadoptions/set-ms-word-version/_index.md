---
title: تعيين إصدار MS Word
linktitle: تعيين إصدار MS Word
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحميل مستند بإصدار محدد من MS Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-loadoptions/set-ms-word-version/
---

عند العمل مع مستندات Word في تطبيق C # ، قد يكون من الضروري تحديد إصدار Microsoft Word لاستخدامه عند تحميل المستند. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تعيين إصدار MS Word الذي تريد استخدامه باستخدام LoadOptions. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام Aspose.Words للكود المصدري .NET C # لتحميل مستند بإصدار محدد من MS Word باستخدام خيارات تحميل LoadOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تكوين خيارات التحميل

الخطوة الأولى هي تكوين خيارات التحميل لوثيقتنا. استخدم فئة LoadOptions لتحديد معلمات التحميل. في حالتنا ، نحتاج إلى ضبط خاصية MswVersion على الإصدار المطلوب من MS Word. على سبيل المثال ، نحن نستخدم إصدار Microsoft Word 2010. إليك كيفية القيام بذلك:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

قمنا بإنشاء كائن LoadOptions جديد وقمنا بتعيين خاصية MswVersion على MsWordVersion.Word2010 لتحديد إصدار MS Word 2010.

## تحميل المستند بإصدار محدد من MS Word

الآن بعد أن قمنا بتكوين خيارات التحميل ، يمكننا تحميل المستند باستخدام فئة Document وتحديد خيارات التحميل. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

في هذا المثال ، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات باستخدام خيارات التحميل المحددة.

### مثال على شفرة المصدر لـ LoadOptions مع وظيفة "Set MS Word Version" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// تكوين خيارات التحميل باستخدام ميزة "تعيين إصدار MS Word"
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// قم بتحميل المستند بالإصدار المحدد من MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// احفظ المستند
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## خاتمة

في هذا الدليل ، أوضحنا كيفية تحميل مستند يحدد إصدارًا معينًا من MS Word باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام مصدر الكود C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يتيح لك تحميل مستند بإصدار محدد من MS Word ضمان التوافق السليم ومعالجة المستند في التطبيق الخاص بك.
