---
title: تحقق من التسلسل
linktitle: تحقق من التسلسل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية التحقق من تسلسل TextBoxes في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-textboxes/check-sequence/
---
يوضح هذا الدليل التفصيلي كيفية التحقق من تسلسل مربعات النصوص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. ستتعلم كيفية تكوين المستند وإنشاء شكل مربع نص والوصول إلى مربعات النص والتحقق من موضعها في التسلسل.

## الخطوة 1: إعداد المستند وإنشاء شكل مربع نص

للبدء ، نحتاج إلى إعداد المستند وإنشاء شكل مربع نص. يقوم الكود التالي بتهيئة مثيل جديد لملف`Document` فئة وإنشاء شكل مربع نص:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## الخطوة 2: التحقق من تسلسل TextBox

 سوف نتحقق الآن من تسلسل استخدام TextBox`if` شروط. يحتوي كود المصدر المقدم على ثلاثة شروط منفصلة للتحقق من موضع TextBox بالنسبة إلى الأشكال السابقة والتالية.

## الخطوة الثالثة: فحص رأس التسلسل:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

إذا كان لمربع النص شكل تالٍ (`Next`) ولكن ليس هناك شكل سابق (`Previous`) ، هذا يعني أنه رأس التسلسل. سيتم عرض رسالة "رأس التسلسل".

## الخطوة 4: فحص منتصف التسلسل:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

إذا كان مربع النص يحتوي على كل من الشكل التالي (`Next`) وشكل سابق (`Previous`) ، يشير هذا إلى أنه في منتصف التسلسل. سيتم عرض الرسالة "منتصف التسلسل".

## الخطوة الخامسة: التحقق من انتهاء التسلسل:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

إذا لم يكن لمربع النص شكل تالٍ (`Next`) ولكن له شكل سابق (`Previous`، هذا يعني أنها نهاية التسلسل. سيتم عرض رسالة "نهاية التسلسل".

### عينة من التعليمات البرمجية المصدر للتحقق من التسلسل باستخدام Aspose.Words for .NET

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

تهنئة ! أنت تعرف الآن كيفية التحقق من تسلسل مربعات النصوص في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات الواردة في هذا الدليل ، تمكنت من إعداد المستند وإنشاء شكل مربع نص والتحقق مما إذا كان في رأس التسلسل أو منتصفه أو نهايته.

### الأسئلة الشائعة للتحقق من التسلسل

#### س: ما هي المكتبة المستخدمة للتحقق من تسلسل مربعات النصوص باستخدام Aspose.Words for .NET؟

ج: للتحقق من تسلسل مربعات النص باستخدام Aspose.Words for .NET ، فإن المكتبة المستخدمة هي Aspose.Words for .NET.

#### س: كيف يمكن تحديد ما إذا كان TextBox هو رأس التسلسل؟

ج: لتحديد ما إذا كان TextBox هو رأس التسلسل ، يمكنك التحقق مما إذا كان يحتوي على النموذج التالي (`Next`) ولكن ليس النموذج السابق (`Previous`). إذا كان الأمر كذلك ، فهذا يعني أنه رأس الخط.

#### س: كيف تعرف ما إذا كان TextBox في منتصف التسلسل؟

ج: لتحديد ما إذا كان TextBox في منتصف التسلسل ، تحتاج إلى التحقق مما إذا كان يحتوي على كلا الشكلين التاليين (`Next`) وشكل سابق (`Previous`). إذا كان الأمر كذلك ، فهذا يشير إلى أنه في منتصف التسلسل.

#### س: كيف تتحقق مما إذا كان TextBox هو نهاية التسلسل؟

ج: للتحقق مما إذا كان TextBox هو نهاية التسلسل ، يمكنك التحقق مما إذا كان لا يحتوي على النموذج التالي (`Next`) ولكن له شكل سابق (`Previous`). إذا كان الأمر كذلك ، فهذا يعني أنها نهاية التسلسل.

#### س: هل يمكننا التحقق من تسلسل العناصر بخلاف مربعات النص؟

ج: نعم ، باستخدام مكتبة Aspose.Words لـ .NET ، من الممكن التحقق من تسلسل العناصر الأخرى مثل الفقرات والجداول والصور وما إلى ذلك. ستختلف العملية اعتمادًا على العنصر المحدد الذي تريد التحقق منه.
