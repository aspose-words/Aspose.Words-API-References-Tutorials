---
title: قائمة مرتبة
linktitle: قائمة مرتبة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء قائمة مرتبة باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/ordered-list/
---

في هذا المثال، سنشرح كيفية استخدام وظيفة القائمة المرتبة مع Aspose.Words for .NET. تسمح لك القائمة المرتبة بتنظيم العناصر بالتسلسل باستخدام الأرقام.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإنشاء مستند جديد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تطبيق تنسيق القائمة المرتبة

 سنقوم بتطبيق تنسيق القائمة المطلوبة باستخدام أداة إنشاء المستندات`ApplyBulletDefault`طريقة. يمكننا أيضًا تخصيص تنسيق الترقيم بالانتقال إلى مستويات القائمة وتعيين التنسيق الذي نريده.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## الخطوة 3: إضافة عناصر إلى القائمة

 يمكننا إضافة عناصر إلى القائمة باستخدام منشئ المستندات`Writeln` طريقة.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## الخطوة 4: المسافة البادئة للقائمة

 يمكننا وضع مسافة بادئة للقائمة باستخدام أداة إنشاء المستندات`ListIndent` طريقة.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## الخطوة 5: حفظ الوثيقة

وأخيرا، يمكننا حفظ المستند بالتنسيق المطلوب.

### مثال على الكود المصدري للقائمة المرتبة باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة القائمة المرتبة مع Aspose.Words for .NET.


### الأسئلة الشائعة

#### س: كيفية إنشاء قائمة مرتبة في تخفيض السعر؟

ج: لإنشاء قائمة مرتبة في Markdown، ابدأ كل عنصر في القائمة برقم متبوع بنقطة (`1.`, `2.`, `3.`)، متبوعة بمسافة.

#### س: هل يمكننا دمج القوائم المرتبة في Markdown؟

ج: نعم، من الممكن دمج القوائم المرتبة في Markdown عن طريق إضافة أربع مسافات إزاحة أمام كل عنصر قائمة متداخل.

#### س: كيفية تخصيص ترقيم القوائم المرتبة؟

ج: في عملية Markdown القياسية، يتم إنشاء ترقيم القائمة المطلوبة تلقائيًا. ومع ذلك، تسمح لك بعض برامج تحرير Markdown بتخصيصها باستخدام امتدادات محددة.

#### س: هل تدعم القوائم المرتبة في Markdown المسافة البادئة؟

ج: نعم، القوائم المرتبة في المسافة البادئة لدعم Markdown. يمكنك إضافة تحول لليسار باستخدام المسافات أو علامات التبويب.

#### س: هل يمكن إضافة الروابط أو النص المضمّن إلى عناصر القائمة؟

ج: نعم، يمكنك إضافة روابط أو نص سطري إلى عناصر القائمة باستخدام صيغة Markdown المناسبة.