---
title: أدخل الحقل المتقدم بدون Document Builder
linktitle: أدخل الحقل المتقدم بدون Document Builder
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل متقدم في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل متقدم بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند والفقرة

نبدأ بإنشاء مستند جديد وجلب الفقرة الأولى.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## الخطوة 3: إدخال الحقل المتقدم

 نحن نستخدم ال`AppendField()`طريقة لإدراج حقل متقدم في الفقرة.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

ثم نقوم بتكوين الخصائص المختلفة للحقل المتقدم من خلال تحديد القيم المطلوبة.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### مثال على الكود المصدري لإدخال حقل متقدم بدون DocumentBuilder مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل الحقل المتقدم.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقلاً متقدمًا دون استخدام DocumentBuilder ، وقمنا بتكوين خصائص الحقل المختلفة ، وحفظنا المستند باسم ملف محدد.

هذا يختتم دليلنا حول كيفية استخدام ميزة "إدراج حقل متقدم بدون DocumentBuilder" مع Aspose.Words for .NET.

