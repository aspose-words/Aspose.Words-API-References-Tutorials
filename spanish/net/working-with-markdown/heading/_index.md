---
title: عنوان
linktitle: عنوان
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام العنوان مع Aspose.Words دليل تفصيلي خطوة بخطوة لـ .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/heading/
---

في هذا المثال ، سوف نوضح لك كيفية استخدام ميزة العناوين مع Aspose.Words for .NET. تُستخدم العناوين لبناء محتوى المستند وتحديد أولوياته.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: تخصيص أنماط العناوين

بشكل افتراضي ، يمكن أن تحتوي أنماط العناوين في Word على تنسيق غامق ومائل. إذا لم نرغب في فرض هذه الخصائص ، فنحن بحاجة إلى تعيينها صراحة على "خطأ".

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## الخطوة 3: إضافة عنوان من المستوى 1

 يمكننا إضافة عنوان من المستوى 1 عن طريق تحديد اسم نمط الفقرة المناسب واستخدام امتداد`Writeln` طريقة كتابة محتوى العنوان.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### مثال على شفرة المصدر للعنوان مع Aspose.Words for .NET


```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// بشكل افتراضي ، قد تحتوي أنماط العناوين في Word على تنسيق غامق ومائل.
	//إذا كنا لا نريد التأكيد ، فاضبط هذه الخصائص صراحةً على false.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");
            
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة العناوين مع Aspose.Words for .NET.


