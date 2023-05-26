---
title: نص مائل
linktitle: نص مائل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية كتابة نص مائل باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /zh/net/working-with-markdown/italic-text/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة النص المائل مع Aspose.Words for .NET. يستخدم النص المائل للتأكيد على أجزاء معينة من المستند.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: اجعل النص مائلًا

 يمكننا جعل النص مائلاً عن طريق تعيين الخط`Italic` ملكية ل`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### مثال على شفرة المصدر للنص المائل باستخدام Aspose.Words for .NET


```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// اجعل النص مائلًا.
	builder.Font.Italic = true;
	builder.Writeln("This text will be Italic");
            
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة النص المائل مع Aspose.Words for .NET.

