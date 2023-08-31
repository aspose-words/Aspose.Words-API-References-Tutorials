---
title: قائمة نقطية
linktitle: قائمة نقطية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء قائمة ذات تعداد نقطي باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/bulleted-list/
---

في هذا البرنامج التعليمي، سنخبرك بكيفية إنشاء قائمة ذات تعداد نقطي باستخدام Aspose.Words لـ .NET. يتم استخدام القائمة ذات التعداد النقطي لسرد العناصر دون استخدام الترقيم.

## الخطوة 1: استخدام منشئ المستندات

أولاً، سنستخدم منشئ المستندات لإضافة محتوى إلى مستندنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: تطبيق القائمة النقطية الافتراضية

 يمكننا تطبيق قائمة نقطية افتراضية باستخدام أداة إنشاء المستندات`ApplyBulletDefault` طريقة.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## الخطوة 3: تخصيص تنسيق التعداد النقطي

 يمكننا تخصيص تنسيق التعداد النقطي من خلال الوصول إلى خصائص`ListFormat.List.ListLevels[0]`. في هذا المثال، نستخدم الشرطة "-" كرصاصة.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## الخطوة 4: إضافة عناصر إلى القائمة

 يمكننا الآن إضافة عناصر إلى القائمة ذات التعداد النقطي باستخدام أداة إنشاء المستندات`Writeln` طريقة.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## الخطوة 5: إزالة المسافة البادئة من القائمة

 إذا أردنا إنشاء قائمة فرعية، يمكننا زيادة المسافة البادئة باستخدام`ListFormat.ListIndent()` طريقة. في هذا المثال، نقوم بإضافة قائمة فرعية إلى العنصرين 2أ و2ب.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### مثال على التعليمات البرمجية المصدر للقائمة النقطية باستخدام Aspose.Words لـ .NET


```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

تهنئة ! لقد تعلمت الآن كيفية إنشاء قائمة ذات تعداد نقطي باستخدام Aspose.Words لـ .NET.

### الأسئلة الشائعة

#### س: كيفية إنشاء قائمة ذات تعداد نقطي في Markdown؟

ج: لإنشاء قائمة ذات تعداد نقطي في Markdown، ابدأ كل عنصر في القائمة برمز نقطي (`-`, `*` ، أو`+`)، متبوعة بمسافة.

#### س: هل يمكنك دمج القوائم النقطية في Markdown؟

ج: نعم، من الممكن دمج القوائم ذات التعداد النقطي في Markdown عن طريق إضافة أربع مسافات إزاحة أمام كل عنصر قائمة متداخل.

#### س: كيفية تخصيص الرموز النقطية؟

ج: في عملية Markdown القياسية، يتم تعريف الرموز النقطية مسبقًا. ومع ذلك، تسمح لك بعض برامج تحرير Markdown بتخصيصها باستخدام امتدادات محددة.

#### س: هل تدعم القوائم النقطية في Markdown المسافة البادئة؟

ج: نعم، تدعم القوائم النقطية في Markdown المسافة البادئة. يمكنك إضافة تحول لليسار باستخدام المسافات أو علامات التبويب.

#### س: هل يمكن إضافة الروابط أو النص المضمّن إلى عناصر القائمة؟

ج: نعم، يمكنك إضافة روابط أو نص سطري إلى عناصر القائمة باستخدام صيغة Markdown المناسبة.
