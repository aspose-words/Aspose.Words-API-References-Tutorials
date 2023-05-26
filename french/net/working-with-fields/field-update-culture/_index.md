---
title: ثقافة التحديث الميداني
linktitle: ثقافة التحديث الميداني
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديث الثقافة الميدانية في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/field-update-culture/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "تحديث الثقافة الميدانية" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند ومُنشئ المستندات

نبدأ بإنشاء مستند جديد ومولد مستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدخال حقل الوقت

 نحن نستخدم ال`InsertField()` طريقة لإدراج حقل الوقت في المستند.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

سيؤدي هذا إلى إدراج حقل الوقت في المستند.

## الخطوة 4: تكوين ثقافة تحديث الحقل

نقوم بتكوين خيارات الحقل لتحديد أن ثقافة تحديث المجال يجب أن تستند إلى رمز الحقل.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

تحدد هذه الخيارات الثقافة المستخدمة لتحديث الحقول.

### نموذج التعليمات البرمجية المصدر لتحديث Field Culture باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند ومُنشئ المستند.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل حقل الوقت.
builder. InsertField(FieldType.FieldTime, true);

// تكوين ثقافة التحديث الميداني.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// احفظ المستند.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقلًا زمنيًا ، وقمنا بتكوين ثقافة تحديث الحقل. ثم قمنا بحفظ المستند باسم ملف محدد.

هذا يختتم دليلنا حول استخدام ميزة "تحديث ثقافة الحقل" مع Aspose.Words for .NET.