---
title: قائمة مرتبة
linktitle: قائمة مرتبة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء قائمة مرتبة باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/ordered-list/
---

في هذا المثال ، سنشرح كيفية استخدام وظيفة القائمة المرتبة مع Aspose.Words for .NET. تتيح لك القائمة المرتبة تنظيم العناصر بالتسلسل باستخدام الأرقام.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإنشاء مستند جديد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تطبيق تنسيق القائمة المرتبة

 سنقوم بتطبيق تنسيق القائمة المرتبة باستخدام منشئ المستندات`ApplyBulletDefault`طريقة. يمكننا أيضًا تخصيص تنسيق الترقيم بالانتقال إلى مستويات القائمة وتعيين التنسيق الذي نريده.

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

## الخطوة 4: مسافة بادئة للقائمة

 يمكننا وضع مسافة بادئة للقائمة باستخدام منشئ المستندات`ListIndent` طريقة.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## الخطوة 5: حفظ المستند

أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب.

### مثال على شفرة المصدر لقائمة مرتبة مع Aspose.Words for .NET

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


### التعليمات

#### س: كيفية إنشاء قائمة مرتبة في Markdown؟

ج: لإنشاء قائمة مرتبة في Markdown ، ابدأ كل عنصر قائمة برقم متبوعًا بنقطة (`1.`, `2.`, `3.`) ، متبوعة بمسافة.

#### س: هل يمكننا وضع قوائم مرتبة في Markdown؟

ج: نعم ، من الممكن تداخل القوائم المرتبة في Markdown عن طريق إضافة أربع مسافات تعويض أمام كل عنصر قائمة متداخل.

#### س: كيف يمكن تخصيص ترقيم القوائم المرتبة؟

ج: في Markdown القياسي ، يتم إنشاء ترقيم القائمة المرتب تلقائيًا. ومع ذلك ، تسمح لك بعض برامج تحرير Markdown بتخصيصه باستخدام امتدادات محددة.

#### س: هل القوائم المرتبة في Markdown تدعم المسافة البادئة؟

ج: نعم ، القوائم المطلوبة في Markdown تدعم المسافة البادئة. يمكنك إضافة وردية اليسار باستخدام المسافات أو علامات التبويب.

#### س: هل يمكن إضافة روابط أو نص مضمّن إلى عناصر القائمة؟

ج: نعم ، يمكنك إضافة روابط أو نص مضمّن إلى عناصر القائمة باستخدام صيغة Markdown المناسبة.