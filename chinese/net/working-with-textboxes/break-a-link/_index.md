---
title: قطع الارتباط
linktitle: قطع الارتباط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية فصل الروابط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET مكتبة قوية تقدم ميزات متنوعة للعمل مع مستندات Microsoft Word برمجيًا. تتمثل إحدى ميزاته المفيدة في القدرة على فصل الروابط داخل المستند. في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري في C # الذي يوضح كيفية قطع الرابط باستخدام Aspose.Words for .NET.

## الخطوة 1: C # Source Code Preview

يركز كود المصدر C # المقدم على ميزة "Break A Link" في Aspose.Words for .NET. يوضح كيفية قطع ارتباط في شكل مربع نص داخل مستند. تقدم الكود سيناريوهات مختلفة لكسر الروابط وتوفر إرشادات واضحة حول كيفية تحقيق النتائج المرجوة.

## الخطوة 2: إعداد المستند وإنشاء شكل مربع نص

 للبدء ، نحتاج إلى إعداد المستند وإنشاء شكل مربع نص. يقوم الكود التالي بتهيئة مثيل جديد لملف`Document` فئة وإنشاء شكل مربع نص:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## الخطوة 3: كسر الرابط في TextBox

 لكسر ارتباط أمامي في TextBox ، يمكننا استخدام`BreakForwardLink()`طريقة. هذه الطريقة تقطع الارتباط بالشكل التالي في التسلسل. يوضح الكود التالي كيفية قطع ارتباط أمامي:

```csharp
textBox.BreakForwardLink();
```

## الخطوة 4: قطع ارتباط أمامي عن طريق تعيين قيمة خالية

 بدلاً من ذلك ، يمكننا قطع ارتباط أمامي عن طريق تعيين TextBox`Next` ملكية ل`null`. هذا يزيل الاتصال بالشكل التالي بشكل فعال. يوضح الكود التالي هذا الأسلوب:

```csharp
textBox. Next = null;
```

## الخطوة 5: قطع الرابط الذي يؤدي إلى TextBox

 في بعض الحالات ، نحتاج إلى قطع ارتباط يؤدي إلى شكل مربع النص. يمكننا تحقيق ذلك من خلال استدعاء`BreakForwardLink()` طريقة على`Previous` النموذج ، الذي يقطع الارتباط إلى TextBox. فيما يلي مثال على كيفية كسر هذا الرابط:

```csharp
textBox.Previous?.BreakForwardLink();
```

### نموذج لشفرة المصدر لكسر الرابط مع Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// كسر الارتباط إلى الأمام.
textBox.BreakForwardLink();

// قطع ارتباط إلى الأمام عن طريق تعيين قيمة خالية.
textBox. Next = null;

// قطع الارتباط الذي يؤدي إلى مربع النص هذا.
textBox.Previous?.BreakForwardLink();
```

