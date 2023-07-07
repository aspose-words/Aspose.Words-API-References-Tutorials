---
title: نص مائل
linktitle: نص مائل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية كتابة نص مائل باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/italic-text/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة النص المائل مع Aspose.Words for .NET. يستخدم النص المائل للتأكيد على أجزاء معينة من المستند.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: اجعل النص مائلًا

 يمكننا جعل النص مائلاً عن طريق تعيين الخط`Italic` الملكية ل`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### مثال على شفرة المصدر للنص المائل باستخدام Aspose.Words for .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// اجعل النص مائلًا.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة النص المائل مع Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكنني كتابة نص مائل في Aspose.Words؟

ج: لجعل النص مائلًا في Aspose.Words ، يمكنك استخدام`Font.Italic` ممتلكات`Run`هدف. يمكنك ضبط هذه الخاصية على`true` لجعل نص معين مائلاً. على سبيل المثال ، يمكنك استخدام ملفات`run.Font.Italic=true` لجعل النص مائلًا في ملف`Run` هدف.

#### س: هل من الممكن جعل عدة أجزاء نصية مائلة في نفس الفقرة؟

 ج: نعم ، يمكنك جعل أجزاء متعددة من النص مائلة في فقرة واحدة باستخدام عدة أجزاء`Run` أشياء. يمكنك إنشاء ملفات`Run` الأشياء وتعيين`Font.Italic` الملكية ل`true` لكل كائن لجعل الأجزاء المطلوبة من النص مائلة. ثم يمكنك إضافتها إلى الفقرة باستخدام`Paragraph.AppendChild(run)` طريقة.

#### س: هل يمكنني كتابة نص مائل في جدول أو خلية في Aspose.Words؟

 ج: نعم ، يمكنك كتابة نص مائل في جدول أو خلية في Aspose.Words. يمكنك الانتقال إلى الخلية أو الفقرة التي تريدها باستخدام الطرق المناسبة ثم تطبيق تنسيق مائل باستخدام`Font.Italic` ممتلكات`Run` أو`Paragraph` هدف.