---
title: يتوسطه خط
linktitle: يتوسطه خط
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/strikethrough/
---


في هذا المثال ، سنرشدك إلى كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام Aspose.Words for .NET. يتم استخدام نص يتوسطه خط للإشارة إلى حذف النص أو أنه لم يعد صالحًا.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: تطبيق نمط النص يتوسطه خط

 سنقوم بتمكين نمط النص يتوسطه خط من خلال تعيين`StrikeThrough`ممتلكات`Font` يعترض على`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## الخطوة 3: أضف نص يتوسطه خط

 يمكننا الآن إضافة نص يتوسطه خط باستخدام منشئ المستندات`Writeln` طريقة.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### مثال على شفرة المصدر لنص يتوسطه خط مع Aspose.Words for .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// اجعل النص يتوسطه خط.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

تهنئة ! لقد تعلمت الآن كيفية تطبيق نمط النص الذي يتوسطه خط باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكنني إضافة نص يتوسطه خط في Aspose.Words؟

 ج: لإضافة نص يتوسطه خط في Aspose.Words ، يمكنك استخدام`Font.StrikeThrough`ممتلكات`Run`هدف. يمكنك ضبط هذه الخاصية على`true` لإضافة نص يتوسطه خط إلى نص معين. على سبيل المثال ، يمكنك استخدام ملفات`run.Font.StrikeThrough=true` لإضافة نص يتوسطه خط إلى ملف`Run` هدف.

#### س: هل من الممكن إضافة نص يتوسطه خط إلى عدة أجزاء من النص في نفس الفقرة؟

 ج: نعم ، يمكنك إضافة نص يتوسطه خط إلى أجزاء متعددة من النص في فقرة واحدة باستخدام عدة`Run` أشياء. يمكنك إنشاء ملفات`Run` الأشياء وتعيين`Font.StrikeThrough` ملكية ل`true`لكل كائن لإضافة نص يتوسطه خط إلى أجزاء النص المطلوبة. ثم يمكنك إضافتها إلى الفقرة باستخدام`Paragraph.AppendChild(run)` طريقة.

#### س: هل يمكنني إضافة نص يتوسطه خط إلى نص موجود في جدول أو خلية في Aspose.Words؟

 ج: نعم ، يمكنك إضافة نص يتوسطه خط إلى نص موجود في جدول أو خلية في Aspose.Words. يمكنك الانتقال إلى الخلية أو الفقرة التي تريدها باستخدام الطرق المناسبة ثم تطبيق تنسيق النص الذي يتوسطه خط باستخدام`Font.StrikeThrough`ممتلكات`Run` أو`Paragraph` هدف.