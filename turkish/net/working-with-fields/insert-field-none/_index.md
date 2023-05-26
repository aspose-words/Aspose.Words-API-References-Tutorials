---
title: إدراج حقل بلا
linktitle: إدراج حقل بلا
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية برنامج Insérez un Champ AUCUN dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-none/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "Insert NONE Field" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder

نبدأ بإنشاء مستند جديد وتهيئة DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدخال حقل NONE

 نحن نستخدم ال`InsertField()` طريقة DocumentBuilder لإدراج حقل NONE في المستند.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### مثال على الكود المصدري لإدخال حقل NONE مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل الحقل NONE.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأعدنا تهيئة DocumentBuilder ، ثم قمنا بإدراج حقل NONE. ثم يتم حفظ المستند باسم ملف محدد.

بهذا نختتم دليلنا حول استخدام ميزة "إدراج NONE Field" مع Aspose.Words for .NET.