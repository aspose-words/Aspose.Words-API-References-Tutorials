---
title: كود مسيجة
linktitle: كود مسيجة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام ميزة التعليمات البرمجية المسيجة مع دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/fenced-code/
---

في هذا المثال، سنرشدك إلى كيفية استخدام ميزة التعليمات البرمجية المسيجة مع Aspose.Words for .NET. يتم استخدام التعليمات البرمجية المسيجة لتمثيل مجموعات من التعليمات البرمجية بتنسيق محدد.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إضافة نمط للتعليمات البرمجية المسيجة

 سنضيف نمطًا مخصصًا للكود المُسيج باستخدام`Styles.Add` طريقة`Document` هدف. في هذا المثال، نقوم بإنشاء نمط يسمى "FencedCode" للتعليمات البرمجية المسيجة.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## الخطوة 3: إضافة كود مسيج بدون معلومات

يمكننا الآن إضافة كتلة تعليمات برمجية مسيجة بدون سلسلة معلومات باستخدام النمط المخصص "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## الخطوة 4: إضافة رمز مسيج مع سلسلة المعلومات

يمكننا أيضًا إضافة كتلة تعليمات برمجية مسيجة تحتوي على سلسلة من المعلومات باستخدام نمط مخصص آخر. في هذا المثال، نقوم بإنشاء نمط يسمى "FencedCode.C#" لتمثيل كتلة من كود C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### مثال على التعليمات البرمجية المصدر للتعليمات المسيجة باستخدام Aspose.Words لـ .NET

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

### الأسئلة الشائعة

#### س: ما هو الكود المحدد في Markdown؟

ج: التعليمات البرمجية المحددة في Markdown هي طريقة تنسيق تستخدم لعرض التعليمات البرمجية في مستند Markdown. وهو يتألف من تأطير التعليمات البرمجية بمحددات محددة.

#### س: ما هي فوائد التعليمات البرمجية المحددة في Markdown؟

ج: تعمل التعليمات البرمجية المحددة في Markdown على تحسين إمكانية قراءة التعليمات البرمجية وتسهل على القراء فهمها. كما يسمح أيضًا بالحفاظ على تمييز بناء الجملة في بعض محررات Markdown.

#### س: ما الفرق بين التعليمات البرمجية المحددة والمسافات البادئة في Markdown؟

ج: تستخدم التعليمات البرمجية المحددة محددات محددة لإحاطة التعليمات البرمجية، بينما تتضمن التعليمات البرمجية ذات المسافة البادئة وضع مسافة بادئة لكل سطر من التعليمات البرمجية بمسافات أو علامات تبويب.

#### س: هل الكود المحدد في Markdown مدعوم من قبل جميع محرري Markdown؟

ج: قد يختلف دعم التعليمات البرمجية المحددة في Markdown بين محرري Markdown. تحقق من الوثائق المحددة للناشر للتأكد.

