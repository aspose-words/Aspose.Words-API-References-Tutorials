---
title: تحقق من التسلسل
linktitle: تحقق من التسلسل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية التحقق من تسلسل TextBoxes في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/check-sequence/
---

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