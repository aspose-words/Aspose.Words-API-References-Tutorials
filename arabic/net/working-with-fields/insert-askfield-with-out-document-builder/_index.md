---
title: أدخل ASKField بدون Document Builder
linktitle: أدخل ASKField بدون Document Builder
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل ASK في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-askfield-with-out-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل ASK بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدخال حقل ASK

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل ASK في الفقرة.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

ثم نقوم بتكوين الخصائص المختلفة لحقل ASK عن طريق تحديد القيم المطلوبة.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### مثال على الكود المصدري لإدخال حقل ASK بدون DocumentBuilder مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل حقل ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقل ASK دون استخدام DocumentBuilder ، وقمنا بتكوين الخصائص المختلفة للحقل ، وحفظنا المستند باسم ملف محدد.

هذا يختتم دليلنا حول استخدام ميزة "إدراج حقل ASK بدون DocumentBuilder" مع Aspose.Words for .NET.