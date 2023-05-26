---
title: نص عريض
linktitle: نص عريض
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية كتابة نص غامق باستخدام Aspose.Words دليل تفصيلي خطوة بخطوة لـ .NET.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bold-text/
---

في هذا المثال ، سنخبرك بكيفية كتابة نص غامق باستخدام Aspose.Words for .NET. النص الغامق يجعله أكثر وضوحًا ويعطيه أهمية أكبر.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: نص عريض

 يمكننا جعل النص غامقًا عن طريق تعيين منشئ المستندات`Font.Bold` ملكية ل`true`.

```csharp
builder.Font.Bold = true;
```

## الخطوة 3: أضف محتوى إلى المستند

 يمكننا الآن إضافة محتوى إلى المستند باستخدام طرق إنشاء المستندات ، مثل`Writeln`، مما يضيف سطرًا من النص.

```csharp
builder.Writeln("This text will be bold");
```

## مثال على كود المصدر للنص الغامق باستخدام Aspose.Words for .NET


```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// اجعل النص غامقًا.
	builder.Font.Bold = true;
	builder.Writeln("This text will be Bold");  
```

تهنئة ! لقد تعلمت الآن كيفية كتابة نص غامق باستخدام Aspose.Words for .NET.


