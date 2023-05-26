---
title: أدخل حقل الدمج باستخدام DOM
linktitle: أدخل حقل الدمج باستخدام DOM
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقول دمج الحقول المخصصة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-merge-field-using-dom/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه والتي تستخدم ميزة "إدراج حقل دمج الحقول" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: تحريك المؤشر إلى الفقرة

 نحن نستخدم ال`MoveTo()` طريقة DocumentBuilder لتحريك المؤشر إلى الفقرة حيث نريد إدراج حقل دمج الحقل.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## الخطوة 4: إدخال حقل دمج الحقول

 نحن نستخدم برنامج DocumentBuilder`InsertField()` طريقة لإدراج حقل دمج حقل في الفقرة.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

نقوم بعد ذلك بتكوين خصائص حقل دمج الحقول عن طريق تحديد الخيارات المناسبة ، مثل اسم الحقل والنص قبل الحقل وبعده وخيارات التنسيق الرأسي.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدخال حقل دمج الحقول مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// حرك المؤشر إلى الفقرة.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// أدخل حقل دمج الحقول.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// قم بتحديث الحقل.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، ونقلنا المؤشر إلى الفقرة المطلوبة ، ثم أدخلنا حقل دمج الحقول في المستند.