---
title: إنشاء ارتباط في Word
linktitle: إنشاء ارتباط في Word
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء ارتباط في Word بين TextBoxes في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-textboxes/create-a-link/
---
يوضح هذا الدليل التفصيلي كيفية إنشاء ارتباط في كلمة بين مربعي نص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. سوف تتعلم كيفية تكوين المستند ، وإنشاء أشكال مربع النص ، والوصول إلى مربعات النص ، والتحقق من صلاحية هدف الارتباط ، وأخيراً إنشاء الارتباط نفسه.

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
## خاتمة

تهنئة ! لقد تعلمت الآن كيفية إنشاء رابط بين مربعي نص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. باستخدام هذا الدليل التفصيلي ، تمكنت من إعداد المستند ، وإنشاء أشكال مربع النص ، والوصول إلى مربعات النص ، والتحقق من صحة هدف الارتباط ، وأخيراً إنشاء الارتباط نفسه.

### الأسئلة الشائعة حول إنشاء ارتباط في Word

#### س: ما هي المكتبة المستخدمة لربط مربعات النص في Word باستخدام Aspose.Words for .NET؟

ج: لربط مربعات النص في Word باستخدام Aspose.Words for .NET ، فإن المكتبة المستخدمة هي Aspose.Words for .NET.

#### س: كيف تتحقق مما إذا كان هدف الارتباط صالحًا قبل إنشاء الارتباط؟

 ج: قبل إنشاء الارتباط بين مربعات النص ، يمكنك استخدام الامتداد`IsValidLinkTarget()` طريقة للتحقق مما إذا كان هدف الارتباط صالحًا. تتحقق هذه الطريقة من إمكانية أن يكون مربع النص الثاني هدفًا صالحًا للارتباط من مربع النص الأول.

#### س: كيف يمكن إنشاء ارتباط بين مربعي نص؟

 ج: لإنشاء ارتباط بين مربعين نصيين ، تحتاج إلى تعيين ملف`Next`الخاصية من مربع النص الأول إلى مربع النص الثاني. تأكد من التحقق من صلاحية رابط الهدف مسبقًا باستخدام`IsValidLinkTarget()` طريقة.

#### س: هل من الممكن إنشاء روابط بين عناصر أخرى غير مربعات النص؟

ج: نعم ، باستخدام مكتبة Aspose.Words لـ .NET ، من الممكن إنشاء روابط بين عناصر مختلفة مثل الفقرات والجداول والصور وما إلى ذلك. ستختلف العملية اعتمادًا على العنصر المحدد الذي ترغب في ربطه.

#### س: ما هي الوظائف الأخرى التي يمكن إضافتها إلى مربعات النص في Word باستخدام Aspose.Words for .NET؟

ج: باستخدام Aspose.Words for .NET ، يمكنك إضافة العديد من الميزات الأخرى إلى مربعات النص ، مثل تنسيق النص وإضافة الصور وتغيير الأنماط وما إلى ذلك. يمكنك استكشاف وثائق Aspose.Words for .NET لاكتشاف جميع الميزات متاح.