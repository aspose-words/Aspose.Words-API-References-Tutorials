---
title: تحميل قاموس الواصلة للغة
linktitle: تحميل قاموس الواصلة للغة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تحميل المستند

أولاً ، قم بتحميل المستند الخاص بك من الدليل المحدد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## الخطوة 2: تحميل قاموس الواصلة

بعد ذلك ، افتح دفقًا إلى ملف قاموس الواصلة واحفظه للغة المطلوبة. في هذا المثال ، نقوم بتحميل قاموس للألمانية السويسرية (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

تأكد من أن لديك ملف القاموس المناسب في دليل البيانات الخاص بك.

## الخطوة 3: احفظ المستند المعدل

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

لذا ! لقد نجحت في تحميل قاموس الواصلة للغة معينة في Aspose.Words for .NET.

### مثال على شفرة المصدر لتحميل قاموس الواصلة للغة باستخدام Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.