---
title: تحميل مستند مشفر
linktitle: تحميل مستند مشفر
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحميل وحفظ المستندات المشفرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/load-encrypted-document/
---

عند العمل مع المستندات المشفرة في تطبيق C # ، من المهم أن تكون قادرًا على تحميلها بشكل صحيح من خلال توفير كلمة المرور الصحيحة. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحميل المستندات المشفرة باستخدام خيارات التحميل المناسبة. في هذا الدليل المفصل خطوة بخطوة ، سنوضح لك كيفية استخدام كود المصدر C # الخاص بـ Aspose.Words for .NET لتحميل مستند مشفر باستخدام خيارات تحميل LoadOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تحميل مستند مشفر

تتمثل الخطوة الأولى في تحميل مستند مشفر باستخدام خيارات التحميل المناسبة. في حالتنا ، نستخدم فئة Document لتحميل المستند عن طريق تحديد مسار المستند وكلمة المرور. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

في هذا المثال ، نقوم بتحميل المستند "Encrypted.docx" الموجود في دليل المستندات باستخدام كلمة المرور "password".

## حفظ مستند مشفر

بعد تحميل مستند مشفر ، يمكنك أيضًا حفظه عن طريق تحديد كلمة مرور جديدة لملف الإخراج. في مثالنا ، نستخدم فئة OdtSaveOptions لحفظ المستند بتنسيق ODT بكلمة مرور جديدة. هيريس كيفية القيام بذلك:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

في هذا المثال ، نحفظ المستند باسم "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" من خلال تحديد كلمة المرور الجديدة "newpassword".

### عينة من التعليمات البرمجية المصدر لـ LoadOptions مع وظيفة "تحميل مستند مشفر" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند مشفر بكلمة المرور المحددة
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//احفظ مستندًا مشفرًا بكلمة مرور جديدة
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## خاتمة

في هذا الدليل ، شرحنا كيفية تحميل وحفظ المستندات المشفرة باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. تحميل المستندات المشفرة يحافظ على أمان بياناتك ويسمح لك بالعمل مع المستندات المحمية في Aspose.Words.