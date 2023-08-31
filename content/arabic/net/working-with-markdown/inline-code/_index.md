---
title: رمز مضمّن
linktitle: رمز مضمّن
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تضمين التعليمات البرمجية باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/inline-code/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة الشفرة المضمنة مع Aspose.Words for .NET. يتم استخدام التعليمات البرمجية المضمنة لتمثيل أجزاء من التعليمات البرمجية بشكل مرئي داخل فقرة.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: أضف نمطًا للرمز المضمَّن

 سنضيف نمطًا مخصصًا للشفرة المضمنة باستخدام امتداد`Styles.Add` طريقة`Document` هدف. في هذا المثال ، نقوم بإنشاء نمط يسمى "InlineCode" للشفرة المضمنة مع علامة خلفية افتراضية.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## الخطوة 3: أضف التعليمات البرمجية المضمنة

الآن يمكننا إضافة التعليمات البرمجية المضمنة باستخدام النمط المخصص "InlineCode". في هذا المثال ، نضيف جزأين من النص بأرقام مختلفة من backticks.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### مثال على شفرة المصدر لـ Inline Code مع Aspose.Words for .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// تم فقدان عدد backticks ، سيتم استخدام علامة خلفية واحدة بشكل افتراضي.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// سيكون هناك 3 باكتيكس.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام وظيفة التعليمات البرمجية المضمنة مع Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكنني استخدام الشفرة المضمنة في Aspose.Words؟

 ج: لاستخدام التعليمات البرمجية المضمنة في Aspose.Words ، يمكنك استخدام العلامات المناسبة لإحاطة النص ليتم تنسيقه على هيئة تعليمات برمجية مضمنة. على سبيل المثال ، يمكنك استخدام ملف`<code>` أو`<kbd>` علامة لإحاطة النص ليتم تنسيقها كرمز مضمّن.

#### س: هل من الممكن تحديد خط الشفرة المضمنة أو لونها في Aspose.Words؟

 ج: نعم ، يمكنك تحديد خط أو لون الشفرة المضمنة في Aspose.Words. يمكنك استخدام ال`Font.Name` و`Font.Color` خصائص`Run` لتعيين خط ولون التعليمات البرمجية المضمنة. على سبيل المثال ، يمكنك استخدام ملفات`run.Font.Name = "Courier New"` لتحديد خط التعليمات البرمجية المضمنة و`run.Font.Color = Color.Blue`لتحديد اللون.

#### س: هل يمكنني استخدام التعليمات البرمجية المضمنة في فقرة تحتوي على عناصر نصية أخرى؟

 ج: نعم ، يمكنك استخدام التعليمات البرمجية المضمنة في فقرة تحتوي على عناصر نصية أخرى. يمكنك إنشاء ملفات`Run` كائنات لتمثيل أجزاء مختلفة من الفقرة ، ثم استخدم علامات التعليمات البرمجية المضمنة لتنسيق الأجزاء المحددة فقط كرمز مضمّن. ثم يمكنك إضافتها إلى الفقرة باستخدام`Paragraph.AppendChild(run)` طريقة.