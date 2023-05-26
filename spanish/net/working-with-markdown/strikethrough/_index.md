---
title: يتوسطه خط
linktitle: يتوسطه خط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /es/net/working-with-markdown/strikethrough/
---


في هذا المثال ، سنرشدك إلى كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام Aspose.Words for .NET. يتم استخدام نص يتوسطه خط للإشارة إلى حذف النص أو أنه لم يعد صالحًا.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: تطبيق نمط النص يتوسطه خط

 سنقوم بتمكين نمط النص يتوسطه خط من خلال تعيين`StrikeThrough` ممتلكات`Font` يعترض على`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## الخطوة 3: أضف نص يتوسطه خط

 يمكننا الآن إضافة نص يتوسطه خط باستخدام منشئ المستندات`Writeln` طريقة.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### مثال على شفرة المصدر لنص يتوسطه خط مع Aspose.Words for .NET

```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// اجعل النص يتوسطه خط.
	builder.Font.StrikeThrough = true;
	builder.Writeln("This text will be StrikeThrough");
            
```

تهنئة ! لقد تعلمت الآن كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام Aspose.Words for .NET.
