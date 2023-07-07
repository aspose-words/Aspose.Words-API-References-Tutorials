---
title: أدخل حقل المؤلف
linktitle: أدخل حقل المؤلف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل AUTHOR في مستندات Word باستخدام Aspose.Words for .NET. حدد اسم المؤلف لتخصيص مستنداتك.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-author-field/
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

### التعليمات

#### س: ما هو مجال المؤلف في Aspose.Words؟

ج: حقل المؤلف في Aspose.Words هو حقل خاص يقوم تلقائيًا بإدراج اسم المؤلف وتحديثه في مستند Word. غالبًا ما يتم استخدامه للإشارة إلى من قام بإنشاء أو تعديل المستند.

#### س: كيف يتم تحديث حقل المؤلف في مستند Word باستخدام Aspose.Words؟

ج: يمكن تحديث حقل المؤلف في مستند Word ليعكس اسم المؤلف الحالي. لهذا ، يمكنك استخدام طريقة UpdateFields المتوفرة في فئة Document. ستعمل هذه الطريقة على تحديث جميع الحقول في المستند ، بما في ذلك حقل المؤلف.

#### س: هل من الممكن تخصيص تنسيق حقل المؤلف في مستند Word؟

ج: نعم ، من الممكن تخصيص تنسيق حقل المؤلف في مستند Word. بشكل افتراضي ، يعرض حقل المؤلف ببساطة اسم المؤلف. ومع ذلك ، يمكنك إضافة معلومات إضافية مثل تاريخ ووقت التعديل باستخدام خيارات التنسيق المتاحة في Aspose.Words.

#### س: هل حقل المؤلف حساس للتغييرات اللاحقة على اسم المؤلف؟

ج: نعم ، حقل المؤلف حساس للتغييرات اللاحقة على اسم المؤلف. إذا قمت بتغيير اسم المؤلف في خصائص المستند ، فسيتم تحديث حقل المؤلف تلقائيًا بالاسم الجديد عند تحديث حقول المستند.