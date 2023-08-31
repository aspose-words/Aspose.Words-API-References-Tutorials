---
title: التحقق من التسلسل
linktitle: التحقق من التسلسل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية التحقق من تسلسل مربعات النص في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-textboxes/check-sequence/
---
يشرح هذا الدليل خطوة بخطوة كيفية التحقق من تسلسل مربعات النص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. سوف تتعلم كيفية تكوين المستند وإنشاء شكل TextBox والوصول إلى TextBoxes والتحقق من موضعها في التسلسل.

## الخطوة 1: إعداد المستند وإنشاء شكل TextBox

 للبدء، نحتاج إلى إعداد المستند وإنشاء شكل TextBox. يقوم التعليمة البرمجية التالية بتهيئة مثيل جديد لـ`Document` فئة وإنشاء شكل مربع نص:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## الخطوة 2: التحقق من تسلسل مربع النص

 سوف نتحقق الآن من تسلسل مربع النص باستخدام`if` شروط. يحتوي الكود المصدري المقدم على ثلاثة شروط منفصلة للتحقق من موضع TextBox بالنسبة للأشكال السابقة والتالية.

## الخطوة 3: التحقق من رأس التسلسل:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

إذا كان TextBox يحتوي على الشكل التالي (`Next`) ولكن لا يوجد شكل سابق (`Previous`)، وهذا يعني أنه رأس التسلسل. سيتم عرض الرسالة "رأس التسلسل".

## الخطوة 4: التحقق من منتصف التسلسل:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

إذا كان مربع النص يحتوي على الشكل التالي (`Next`) وشكل سابق (`Previous`)، وهذا يدل على أنه في منتصف التسلسل. سيتم عرض الرسالة "منتصف التسلسل".

## الخطوة الخامسة: التحقق من نهاية التسلسل:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

إذا لم يكن لدى TextBox الشكل التالي (`Next`) ولكن له شكل سابق (`Previous`)، وهذا يعني أنها نهاية التسلسل. سيتم عرض الرسالة "نهاية التسلسل".

### نموذج التعليمات البرمجية المصدر للتحقق من التسلسل باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية التحقق من تسلسل مربعات النص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات الواردة في هذا الدليل، تمكنت من إعداد المستند وإنشاء شكل TextBox والتحقق مما إذا كان موجودًا في رأس التسلسل أو وسطه أو نهايته.

### الأسئلة الشائعة للتحقق من التسلسل

#### س: ما هي المكتبة المستخدمة للتحقق من تسلسل مربعات النص باستخدام Aspose.Words لـ .NET؟

ج: للتحقق من تسلسل مربعات النص باستخدام Aspose.Words لـ .NET، المكتبة المستخدمة هي Aspose.Words لـ .NET.

#### س: كيفية تحديد ما إذا كان TextBox هو رأس التسلسل؟

ج: لتحديد ما إذا كان TextBox هو رأس التسلسل، يمكنك التحقق مما إذا كان يحتوي على النموذج التالي (`Next`) ولكن ليس النموذج السابق (`Previous`). إذا كان الأمر كذلك، فهذا يعني أنه رأس الخط.

#### س: كيف يمكن معرفة ما إذا كان TextBox موجودًا في منتصف التسلسل؟

ج: لتحديد ما إذا كان مربع النص موجودًا في منتصف التسلسل، فأنت بحاجة إلى التحقق مما إذا كان يحتوي على الشكل التالي (`Next`) وشكل سابق (`Previous`). إذا كان الأمر كذلك، فهذا يشير إلى أنه في منتصف التسلسل.

#### س: كيف يمكن التحقق مما إذا كان TextBox هو نهاية التسلسل؟

ج: للتحقق مما إذا كان مربع النص هو نهاية التسلسل، يمكنك التحقق مما إذا كان لا يحتوي على النموذج التالي (`Next`) ولكن لديه نموذج سابق (`Previous`). إذا كان الأمر كذلك، فهذا يعني أنها نهاية التسلسل.

#### س: هل يمكننا التحقق من تسلسل العناصر بخلاف TextBoxes؟

ج: نعم، باستخدام مكتبة Aspose.Words لـ .NET، من الممكن التحقق من تسلسل العناصر الأخرى مثل الفقرات والجداول والصور وما إلى ذلك. ستختلف العملية وفقًا للعنصر المحدد الذي تريد التحقق منه.
