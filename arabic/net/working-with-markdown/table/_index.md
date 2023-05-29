---
title: طاولة
linktitle: طاولة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/table/
---


في هذا المثال ، سنرشدك إلى كيفية إنشاء جدول باستخدام Aspose.Words for .NET. الجدول عبارة عن هيكل بيانات ينظم المعلومات في صفوف وأعمدة.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## الخطوة 2: أضف الخلايا والبيانات

 سنضيف خلايا وبيانات إلى جدولنا باستخدام`InsertCell` الطريقة و`Writeln` طريقة منشئ الوثيقة.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### مثال على شفرة المصدر لإنشاء جدول باستخدام Aspose.Words for .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// أضف الصف الأول.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// أضف الصف الثاني.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

تهنئة ! لقد تعلمت الآن كيفية إنشاء جدول باستخدام Aspose.Words for .NET.
