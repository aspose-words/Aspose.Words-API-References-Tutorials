---
title: عنوان Setext
linktitle: عنوان Setext
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام عناوين Setext لتنسيق مستنداتك باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/setext-heading/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام ميزة Setext Heading مع Aspose.Words for .NET. Setext Heading هي طريقة بديلة لتنسيق العناوين في مستندات Markdown.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: استخدام نمط عنوان Setext

سنستخدم نمط الفقرة الافتراضي "العنوان 1" لإنشاء عنوان من المستوى 1 في وثيقتنا.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## الخطوة 3: إعادة ضبط الأنماط

نقوم بإعادة تعيين أنماط الخطوط المطبقة مسبقًا لتجنب أي مجموعة غير مرغوب فيها من الأنماط بين الفقرات.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## الخطوة 4: تخصيص مستويات عناوين Setext

يمكننا تخصيص مستويات عناوين Setext عن طريق إضافة أنماط فقرة جديدة بناءً على أنماط العناوين الحالية. في هذا المثال ، نقوم بإنشاء نمط "SetextHeading1" استنادًا إلى نمط "العنوان 1" لتمثيل عنوان المستوى 1 بتنسيق Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## الخطوة 5: حفظ المستند

أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### مثال على شفرة المصدر لعناوين Setext مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// إعادة تعيين الأنماط من الفقرة السابقة لعدم دمج الأنماط بين الفقرات.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// إعادة تعيين الأنماط من الفقرة السابقة لعدم دمج الأنماط بين الفقرات.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// ستتم إعادة تعيين مستوى عنوان Setex إلى 2 إذا كانت الفقرة الأساسية بها مستوى عنوان أكبر من 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### التعليمات

#### س: ما هو رأس Setext Markdown؟

ج: رأس Setext Markdown هو طريقة بديلة لإنشاء عناوين في مستند Markdown. يستخدم أحرف التسطير السفلي (= أو -) للإشارة إلى مستويات مختلفة من العناوين.

#### س: كيفية استخدام رؤوس Setext Markdown؟

ج: لاستخدام عناوين Setext Markdown ، ضع الشرطة السفلية أسفل نص العنوان. استخدم علامات التساوي (=) لرأس المستوى 1 والواصلات (-) لرأس المستوى 2.

#### س: هل هناك أي قيود على استخدام رؤوس Setext Markdown؟

ج: تحتوي عناوين Setext Markdown على قيود من حيث التسلسل الهرمي للعناوين وليست مميزة بصريًا مثل عناوين Markdown القياسية.

#### س: هل يمكنني تخصيص مظهر رؤوس Setext Markdown؟

ج: في Markdown القياسي ، لا يمكن تخصيص مظهر رؤوس Setext Markdown. لديهم مظهر محدد مسبقًا استنادًا إلى الأحرف السفلية المستخدمة.

#### س: هل رؤوس Setext Markdown مدعومة من قبل جميع محرري Markdown؟

ج: قد يختلف دعم رؤوس Setext Markdown بين محرري Markdown. تحقق من وثائق الناشر الخاصة بك للتأكد.