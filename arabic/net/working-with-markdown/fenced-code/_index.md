---
title: كود مسيّج
linktitle: كود مسيّج
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام ميزة الشفرة المسيجة مع دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/fenced-code/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة الشفرة المسيجة مع Aspose.Words for .NET. يتم استخدام الكود المسيج لتمثيل كتل من التعليمات البرمجية بتنسيق محدد.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إضافة نمط للرمز المسيَّج

 سنضيف نمطًا مخصصًا للشفرة المسيجة باستخدام امتداد`Styles.Add` طريقة`Document` هدف. في هذا المثال ، نقوم بإنشاء نمط يسمى "FencedCode" للرمز المسيَّج.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## الخطوة 3: إضافة كود مسيّج بدون معلومات

الآن يمكننا إضافة كتلة رمز مسيجة بدون سلسلة معلومات باستخدام النمط المخصص "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## الخطوة 4: إضافة رمز مسيَّج بسلسلة المعلومات

يمكننا أيضًا إضافة كتلة تعليمات برمجية مسيجة بسلسلة من المعلومات باستخدام نمط مخصص آخر. في هذا المثال ، نقوم بإنشاء نمط يسمى "FencedCode.C #" لتمثيل كتلة من كود C #.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### مثال لشفرة المصدر لـ Fined Code باستخدام Aspose.Words for .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### التعليمات

#### س: ما هو الرمز المحدد في Markdown؟

ج: التعليمات البرمجية المحددة في Markdown هي طريقة تنسيق تُستخدم لعرض التعليمات البرمجية في مستند Markdown. يتكون من تأطير الكود بمحددات محددة.

#### س: ما هي فوائد الكود المحدد في Markdown؟

ج: تعمل التعليمات البرمجية المحددة في Markdown على تحسين إمكانية قراءة التعليمات البرمجية وتسهيل فهمها للقراء. كما يسمح بالحفاظ على إبراز بناء الجملة في بعض محرري Markdown.

#### س: ما الفرق بين التعليمات البرمجية المحددة والمسافات البادئة في Markdown؟

ج: يستخدم الكود المحدد محددات محددة لإحاطة الكود ، بينما يتضمن الكود ذي المسافة البادئة المسافة البادئة لكل سطر من التعليمات البرمجية بمسافات أو علامات تبويب.

#### س: هل الكود المحدد في Markdown مدعوم من قبل جميع محرري Markdown؟

ج: قد يختلف دعم التعليمات البرمجية المحددة في Markdown بين محرري Markdown. تحقق من وثائق الناشر الخاصة بك للتأكد.

