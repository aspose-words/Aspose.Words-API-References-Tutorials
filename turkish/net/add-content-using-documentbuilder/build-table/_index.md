---
title: بناء الجدول
linktitle: بناء الجدول
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/build-table/
---

في هذا البرنامج التعليمي خطوة بخطوة ، ستتعلم كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إنشاء جدول بتنسيق ومحتوى مخصصين باستخدام فئة DocumentBuilder.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بإنشاء مستند جديد
للبدء ، أنشئ مستندًا جديدًا باستخدام فئة المستند:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: ابدأ الجدول
بعد ذلك ، استخدم طريقة StartTable لفئة DocumentBuilder لبدء إنشاء الجدول:

```csharp
Table table = builder.StartTable();
```

## الخطوة 3: أدخل الخلايا وأضف المحتوى
الآن ، يمكنك إدراج خلايا في الجدول وإضافة محتوى إليها باستخدام أساليب InsertCell و Write لفئة DocumentBuilder. قم بتخصيص تنسيق الخلية حسب الحاجة:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## الخطوة 4: قم بإنهاء الصف
بعد إضافة محتوى إلى خلايا الصف الأول ، استخدم طريقة EndRow لفئة DocumentBuilder لإنهاء الصف:

```csharp
builder.EndRow();
```

## الخطوة 5: تخصيص تنسيق الصفوف
يمكنك تخصيص تنسيق الصف عن طريق تعيين خصائص كائنات RowFormat و CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## الخطوة 6: قم بإنهاء الجدول
لإكمال الجدول ، استخدم طريقة EndTable لفئة DocumentBuilder:

```csharp
builder.EndTable();
```

### مثال كود المصدر لبناء جدول باستخدام Aspose.Words for .NET
إليك الكود المصدري الكامل لبناء جدول باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إنشاء جداول بتنسيق مخصص.