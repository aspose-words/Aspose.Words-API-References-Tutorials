---
title: قائمة نقطية
linktitle: قائمة نقطية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء قائمة نقطية باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ru/net/working-with-markdown/bulleted-list/
---

في هذا البرنامج التعليمي ، سنخبرك بكيفية إنشاء قائمة نقطية باستخدام Aspose.Words for .NET. يتم استخدام قائمة نقطية لسرد العناصر بدون استخدام الترقيم.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: تطبيق قائمة نقطية افتراضية

 يمكننا تطبيق قائمة افتراضية ذات تعداد نقطي باستخدام قائمة منشئ المستندات`ApplyBulletDefault` طريقة.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## الخطوة 3: تخصيص تنسيق الرمز النقطي

 يمكننا تخصيص تنسيق الرمز النقطي من خلال الوصول إلى خصائص`ListFormat.List.ListLevels[0]`. في هذا المثال ، نستخدم الشرطة "-" كرمز نقطي.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## الخطوة 4: إضافة عناصر إلى القائمة

 يمكننا الآن إضافة عناصر إلى القائمة النقطية باستخدام أداة إنشاء المستندات`Writeln` طريقة.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## الخطوة 5: إزالة المسافة البادئة من القائمة

 إذا أردنا إنشاء قائمة فرعية ، فيمكننا زيادة المسافة البادئة باستخدام`ListFormat.ListIndent()` طريقة. في هذا المثال ، نضيف قائمة فرعية إلى البندين 2 أ و 2 ب.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### مثال على شفرة المصدر لقائمة التعداد النقطي باستخدام Aspose.Words for .NET


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

تهنئة ! لقد تعلمت الآن كيفية إنشاء قائمة نقطية باستخدام Aspose.Words for .NET.

