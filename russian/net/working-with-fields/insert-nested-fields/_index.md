---
title: أدخل الحقول المتداخلة
linktitle: أدخل الحقول المتداخلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الحقول المتداخلة بسهولة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-nested-fields/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج الحقول المتداخلة" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدراج فواصل الصفحات

نستخدم حلقة لإدراج عدة فواصل صفحات في المستند.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## الخطوة 4: الانتقال إلى التذييل

 نحن نستخدم ال`MoveToHeaderFooter()` أسلوب DocumentBuilder لتحريك المؤشر إلى التذييل الرئيسي.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## الخطوة 5: إدخال الحقل المتداخل

 نحن نستخدم برنامج DocumentBuilder`InsertField()` طريقة لإدراج حقل متداخل في التذييل.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدخال الحقول المتداخلة مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل فواصل الصفحات.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// الانتقال إلى التذييل.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// أدخل الحقل المتداخل.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// قم بتحديث الحقل.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدرجنا فواصل الصفحات ، وحركنا المؤشر إلى التذييل ، ثم أدرجنا حقلاً متداخلًا في التذييل.