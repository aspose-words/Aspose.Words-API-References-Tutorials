---
title: يقتبس
linktitle: يقتبس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام الاقتباس مع Aspose.Words دليل تفصيلي خطوة بخطوة لـ .NET.
type: docs
weight: 10
url: /de/net/working-with-markdown/quote/
---

في هذا المثال ، سنشرح كيفية استخدام ميزة الاقتباس مع Aspose.Words for .NET Quote تُستخدم لإبراز أقسام النص من خلال إحاطةهم بحد خاص.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة الثانية: استخدام أسلوب الاقتباس الافتراضي

سنستخدم نمط الفقرة الافتراضي المسمى "اقتباس" لتطبيق تنسيق الاقتباس على النص.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## الخطوة 3: إنشاء أنماط للمستويات المتداخلة

 يمكننا إنشاء أنماط للمستويات المتداخلة باستخدام امتداد`Styles.Add` طريقة`Document` هدف. في هذا المثال ، نقوم بإنشاء نمط يسمى "Quote1" لتمثيل مستوى اقتباس متداخل.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### مثال على شفرة المصدر للاقتباسات باستخدام Aspose.Words for .NET


```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// بشكل افتراضي ، يخزن المستند نمط blockquote للمستوى الأول.
	builder.ParagraphFormat.StyleName = "Quote";
	builder.Writeln("Blockquote");

	// إنشاء أنماط للمستويات المتداخلة من خلال وراثة النمط.
	Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
	builder.ParagraphFormat.Style = quoteLevel2;
	builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
	builder.Writeln("1. Nested blockquote");
            
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الاقتباسات مع Aspose.Words for .NET.

