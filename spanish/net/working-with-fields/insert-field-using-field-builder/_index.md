---
title: أدخل الحقل باستخدام Field Builder
linktitle: أدخل الحقل باستخدام Field Builder
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الحقول المخصصة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-using-field-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل باستخدام FieldBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

نبدأ بإنشاء مستند جديد.

```csharp
Document doc = new Document();
```

## الخطوة 3: بناء حقل IF باستخدام FieldBuilder

نستخدم فئة FieldBuilder لإنشاء حقل IF مع حقلي MERGEFIELD متداخلين. في هذا المثال ، يعرض الحقل IF الاسم الأول والأخير بناءً على شرط.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## الخطوة 4: إدخال حقل IF في المستند

 نحن نستخدم ال`BuildAndInsert()` طريقة لإنشاء وإدراج حقل IF في موقع محدد في المستند.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### مثال على شفرة المصدر لإدخال حقل باستخدام FieldBuilder مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();

// إنشاء حقل IF باستخدام FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// أدخل حقل IF في المستند.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأنشأنا حقل IF مع حقول MERGEFIELD المتداخلة ، ثم قمنا بإدراج هذا الحقل في المستند في موقع محدد. ثم يتم حفظ المستند باسم ملف محدد.
