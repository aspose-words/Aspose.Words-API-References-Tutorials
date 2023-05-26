---
title: رمز مسافة بادئة
linktitle: رمز مسافة بادئة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام التعليمات البرمجية ذات المسافات البادئة مع دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /sv/net/working-with-markdown/indented-code/
---

في هذا المثال ، سنشرح كيفية استخدام ميزة الشفرة ذات المسافة البادئة مع Aspose.Words for .NET. يتم استخدام التعليمات البرمجية ذات المسافة البادئة لتمثيل كتل التعليمات البرمجية بصريًا بتنسيق محدد.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: أضف نمطًا للرمز ذي المسافة البادئة

 سنضيف نمطًا مخصصًا للشفرة ذات المسافة البادئة باستخدام امتداد`Styles.Add` طريقة`Document` هدف. في هذا المثال ، نقوم بإنشاء نمط يسمى "IndentedCode" للشفرة ذات المسافة البادئة.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## الخطوة 3: أضف التعليمات البرمجية ذات المسافة البادئة

الآن يمكننا إضافة كتلة تعليمات برمجية ذات مسافة بادئة باستخدام النمط المخصص "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### مثال على شفرة المصدر للتعليمات البرمجية ذات المسافات البادئة باستخدام Aspose.Words for .NET

```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
	builder.ParagraphFormat.Style = indentedCode;
	builder.Writeln("This is an indented code");
            
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الشفرة ذات المسافة البادئة مع Aspose.Words for .NET.

