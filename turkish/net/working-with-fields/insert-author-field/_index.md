---
title: أدخل حقل المؤلف
linktitle: أدخل حقل المؤلف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل AUTHOR في مستندات Word باستخدام Aspose.Words for .NET. حدد اسم المؤلف لتخصيص مستنداتك.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-author-field/
---


فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود المصدر C # أدناه ، والذي يستخدم ميزة "إدراج حقل مؤلف" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: أدخل حقل AUTHOR

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل AUTHOR في الفقرة.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 ثم نقوم بتكوين المجال`AuthorName` الخاصية لتحديد اسم المؤلف.

```csharp
field. AuthorName = "Test1";
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### مثال على شفرة المصدر لإدخال حقل AUTHOR مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل حقل AUTHOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقل AUTHOR ، وضبطنا اسم المؤلف ، وحفظنا المستند باسم ملف محدد.

بهذا يختتم دليلنا حول استخدام ميزة "إدراج حقل المؤلف" مع Aspose.Words for .NET.
