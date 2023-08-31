---
title: يقتبس
linktitle: يقتبس
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام الاقتباس مع دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/quote/
---

في هذا المثال، سنشرح كيفية استخدام ميزة الاقتباس مع Aspose. يتم استخدام الكلمات الخاصة بـ .NET Quote لتمييز أجزاء من النص من خلال إحاطتها بحدود خاصة.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: استخدام نمط الاقتباس الافتراضي

سنستخدم نمط الفقرة الافتراضي المسمى "اقتباس" لتطبيق تنسيق الاقتباس على النص.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## الخطوة 3: إنشاء أنماط للمستويات المتداخلة

 يمكننا إنشاء أنماط للمستويات المتداخلة باستخدام`Styles.Add` طريقة`Document` هدف. في هذا المثال، نقوم بإنشاء نمط يسمى "Quote1" لتمثيل مستوى الاقتباس المتداخل.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### مثال على التعليمات البرمجية المصدر للاستشهادات باستخدام Aspose.Words لـ .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// بشكل افتراضي، يقوم المستند بتخزين نمط الاقتباس للمستوى الأول.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// إنشاء أنماط للمستويات المتداخلة من خلال وراثة النمط.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الاستشهادات مع Aspose.Words for .NET.


### الأسئلة الشائعة

#### س: ما هو الاقتباس في تخفيض السعر؟

ج: الاقتباس في Markdown هو وسيلة لتسليط الضوء على مقاطع نصية من مصادر أخرى أو للإشارة إلى الاقتباسات الشهيرة.

#### س: كيفية استخدام علامات الاقتباس في تخفيض السعر؟

ج: لاستخدام الاقتباس في Markdown، قم بإحاطة نص الاقتباس بين قوسين زاوية (`>`). يجب أن يبدأ كل سطر من الاقتباس بشيفرون.

#### س: هل تدعم علامات الاقتباس Markdown السمات؟

ج: لا تدعم استشهادات تخفيض السعر سمات محددة. يتم تسليط الضوء عليها ببساطة من خلال تنسيق النص المقتبس.

#### س: هل يمكنك تضمين علامات الاقتباس في Markdown؟

ج: نعم، من الممكن دمج علامات الاقتباس في Markdown عن طريق إضافة مستوى إضافي من الأقواس الزاوية (`>`).