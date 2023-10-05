---
title: التأكيدات
linktitle: التأكيدات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام التوكيدات (الخط العريض والمائل) باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/emphases/
---

في هذا المثال، سنشرح كيفية استخدام التوكيدات مع Aspose.Words لـ .NET. يتم استخدام التوكيد للتأكيد على أجزاء معينة من النص، مثل الخط العريض والمائل.

## الخطوة 1: تهيئة المستند

 أولاً، سنقوم بتهيئة المستند عن طريق إنشاء مثيل لـ`Document` فصل.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: استخدام منشئ المستندات

بعد ذلك، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة نص مع التأكيدات

يمكننا إضافة نص التأكيدات عن طريق تغيير خصائص الخط الخاص بمولد المستندات. في هذا المثال، نستخدم الخط العريض والمائل للتأكيد على أجزاء مختلفة من النص.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## الخطوة 4: حفظ الوثيقة

 وأخيرا، يمكننا حفظ المستند بالتنسيق المطلوب. في هذا المثال نستخدم`.md` امتداد لتنسيق Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام التوكيدات مع Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر للتأكيدات باستخدام Aspose.Words لـ .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### الأسئلة الشائعة

#### س: كيف يمكنني تمييز النص باستخدام Markdown؟

 ج: لتمييز النص باستخدام Markdown، ما عليك سوى إحاطة النص بالرموز المناسبة. يستخدم`*` أو`_` للخط المائل،`**` أو`__` للجريئة، و`~~` للتوسط.

#### س: هل يمكننا الجمع بين النقاط البارزة المختلفة في نفس النص؟

 ج: نعم، من الممكن الجمع بين النقاط البارزة المختلفة في نفس النص. على سبيل المثال، يمكنك كتابة الكلمة بخط غامق ومائل باستخدام كليهما`**` و`*`حول العالم.

#### س: ما هي خيارات التمييز المتوفرة في Markdown؟

ج: خيارات التمييز المتوفرة في Markdown مائلة (`*` أو`_`)، عريض (`**` أو`__`) ، ويتوسطه خط (`~~`).

#### س: كيف أتعامل مع الحالات التي يحتوي فيها النص على أحرف خاصة يستخدمها Markdown للتمييز؟

 ج: إذا كان النص الخاص بك يحتوي على أحرف خاصة يستخدمها Markdown للتمييز، فيمكنك الهروب منها عن طريق وضع علامة قبلها`\` . على سبيل المثال،`\*` سيتم عرض علامة النجمة الحرفية.

#### س: هل يمكننا تخصيص مظهر التمييز باستخدام CSS؟

ج: عادةً ما يتم عرض التمييز في Markdown باستخدام الأنماط الافتراضية للمتصفح. إذا قمت بتحويل Markdown إلى HTML، فيمكنك تخصيص مظهر التمييز باستخدام قواعد CSS.