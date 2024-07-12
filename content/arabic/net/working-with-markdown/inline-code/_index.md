---
title: كود مضمن
linktitle: كود مضمن
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تضمين التعليمات البرمجية باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/inline-code/
---

في هذا المثال، سنرشدك إلى كيفية استخدام ميزة التعليمات البرمجية المضمّنة مع Aspose.Words for .NET. يتم استخدام Inline Code لتمثيل أجزاء من التعليمات البرمجية بشكل مرئي داخل الفقرة.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: إضافة نمط للتعليمات البرمجية المضمنة

 سنضيف نمطًا مخصصًا للكود المضمّن باستخدام ملف`Styles.Add` طريقة`Document` هدف. في هذا المثال، نقوم بإنشاء نمط يسمى "InlineCode" للتعليمات البرمجية المضمنة باستخدام علامة خلفية افتراضية.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## الخطوة 3: إضافة التعليمات البرمجية المضمنة

يمكننا الآن إضافة كود مضمّن باستخدام النمط المخصص "InlineCode". في هذا المثال، قمنا بإضافة قطعتين من النص بأعداد مختلفة من العلامات الخلفية.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### مثال على التعليمات البرمجية المصدر للتعليمات البرمجية المضمنة مع Aspose.Words لـ .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// تم تفويت عدد من النقرات الخلفية، وسيتم استخدام علامة واحدة بشكل افتراضي.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// سيكون هناك 3 backticcks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام وظيفة التعليمات البرمجية المضمنة مع Aspose.Words لـ .NET.


### الأسئلة الشائعة

#### س: كيف يمكنني استخدام التعليمات البرمجية المضمنة في Aspose.Words؟

 ج: لاستخدام التعليمات البرمجية المضمنة في Aspose.Words، يمكنك استخدام العلامات المناسبة لإحاطة النص المراد تنسيقه كرمز مضمّن. على سبيل المثال، يمكنك استخدام`<code>` أو`<kbd>` وضع علامة على النص المحيطي ليتم تنسيقه كرمز مضمّن.

#### س: هل من الممكن تحديد خط أو لون التعليمات البرمجية المضمنة في Aspose.Words؟

 ج: نعم، يمكنك تحديد خط أو لون التعليمات البرمجية المضمنة في Aspose.Words. يمكنك استخدام ال`Font.Name`و`Font.Color` خصائص`Run` كائن لتعيين الخط ولون التعليمات البرمجية المضمنة. على سبيل المثال، يمكنك استخدام`run.Font.Name = "Courier New"` لتحديد الخط للتعليمات البرمجية المضمنة و`run.Font.Color = Color.Blue`لتحديد اللون.

#### س: هل يمكنني استخدام التعليمات البرمجية المضمنة في فقرة تحتوي على عناصر نصية أخرى؟

 ج: نعم، يمكنك استخدام التعليمات البرمجية المضمنة في فقرة تحتوي على عناصر نصية أخرى. يمكنك إنشاء عدة`Run` كائنات لتمثيل أجزاء مختلفة من الفقرة، ثم استخدم علامات التعليمات البرمجية المضمنة لتنسيق الأجزاء المحددة فقط كرمز مضمن. ثم يمكنك إضافتها إلى الفقرة باستخدام`Paragraph.AppendChild(run)` طريقة.