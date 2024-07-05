---
title: عنوان النص
linktitle: عنوان النص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام عناوين Setext لتنسيق مستنداتك باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/setext-heading/
---

في هذا البرنامج التعليمي، سنرشدك إلى كيفية استخدام ميزة Setext Heading مع Aspose.Words for .NET. يعد Setext Heading طريقة بديلة لتنسيق العناوين في مستندات Markdown.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: استخدام نمط عنوان Settext

سنستخدم نمط الفقرة الافتراضي "العنوان 1" لإنشاء عنوان المستوى 1 في وثيقتنا.

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

## الخطوة 4: تخصيص مستويات عنوان Settext

يمكننا تخصيص مستويات عناوين Setext عن طريق إضافة أنماط فقرات جديدة بناءً على أنماط العناوين الموجودة. في هذا المثال، نقوم بإنشاء نمط "SetextHeading1" استنادًا إلى نمط "العنوان 1" لتمثيل عنوان المستوى 1 في تنسيق Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## الخطوة 5: حفظ الوثيقة

وأخيرا، يمكننا حفظ المستند بالتنسيق المطلوب.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### مثال على التعليمات البرمجية المصدر لعناوين Setext مع Aspose.Words لـ .NET

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

// سيتم إعادة تعيين مستوى عنوان Setex إلى 2 إذا كانت الفقرة الأساسية تحتوي على مستوى عنوان أكبر من 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### الأسئلة الشائعة

#### س: ما هو رأس Setex Markdown؟

ج: يعد رأس Setext Markdown طريقة بديلة لإنشاء عناوين في مستند Markdown. ويستخدم الشرطة السفلية (= أو -) للإشارة إلى مستويات مختلفة من العناوين.

#### س: كيفية استخدام رؤوس Setex Markdown؟

ج: لاستخدام عناوين Setext Markdown، ضع الشرطة السفلية أسفل نص العنوان. استخدم علامات المساواة (=) لرأس المستوى 1 والواصلات (-) لرأس المستوى 2.

#### س: هل هناك أي قيود في استخدام رؤوس Setex Markdown؟

ج: تحتوي عناوين Setext Markdown على قيود من حيث التسلسل الهرمي للعناوين وليست متميزة بصريًا مثل عناوين Markdown القياسية.

#### س: هل يمكنني تخصيص مظهر رؤوس Settext Markdown؟

ج: في Markdown القياسي، ليس من الممكن تخصيص مظهر رؤوس Setext Markdown. لديهم مظهر محدد مسبقًا استنادًا إلى الأحرف السفلية المستخدمة.

#### س: هل رؤوس Settext Markdown مدعومة من قبل جميع محرري Markdown؟

ج: قد يختلف دعم رؤوس Settext Markdown بين محرري Markdown. تحقق من الوثائق المحددة للناشر للتأكد.