---
title: إنشاء ارتباط
linktitle: إنشاء ارتباط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء رابط بين TextBoxes في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/create-a-link/
---

## الخطوة 1: إعداد المستند وإنشاء أشكال TextBox

 للبدء ، نحتاج إلى إعداد المستند وإنشاء شكلين مربع نص. يقوم الكود التالي بتهيئة مثيل جديد لملف`Document` فئة وإنشاء شكلين لمربع النص:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## الخطوة 2: إنشاء ارتباط بين مربعات النص

 سنقوم الآن بإنشاء رابط بين مربعي النص باستخدام امتداد`IsValidLinkTarget()` الطريقة و`Next` خاصية TextBox الأول.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 ال`IsValidLinkTarget()` يتحقق الأسلوب مما إذا كان يمكن أن يكون TextBox الثاني هدفًا صالحًا للارتباط الخاص بـ TextBox الأول. إذا نجح التحقق من الصحة ، فإن`Next` تم تعيين خاصية TextBox الأول على TextBox الثاني ، مما يؤدي إلى إنشاء ارتباط بين الاثنين.

### مثال على شفرة المصدر للارتباط بـ Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```