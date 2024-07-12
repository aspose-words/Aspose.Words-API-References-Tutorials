---
title: كرر الصفوف في الصفحات اللاحقة
linktitle: كرر الصفوف في الصفحات اللاحقة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تكرار صفوف الجدول في الصفحات اللاحقة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية تكرار صفوف الجدول في الصفحات اللاحقة من مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستتمكن من تحديد الصفوف التي تريد تكرارها في الصفحات اللاحقة من الجدول الخاص بك في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستندات
لبدء معالجة الكلمات باستخدام منشئ المستندات والمستندات، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// تهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: بناء الجدول بالصفوف المتكررة
بعد ذلك، سنقوم بإنشاء جدول يحتوي على صفوف متكررة في الصفحات اللاحقة. استخدم الكود التالي:

```csharp
// بداية الجدول
builder. StartTable();

// تكوين معلمات السطر الأول (خطوط الرأس)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//أدخل الخلية الأولى من الصف الأول
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// أدخل الخلية الثانية من الصف الأول
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// تكوين معلمات الأسطر التالية
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// قم بإجراء حلقة لإدراج الخلايا في الصفوف التالية
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// نهاية الجدول
builder. EndTable();
```

 نستخدم هنا أداة إنشاء المستندات لإنشاء جدول يحتوي على صفين للرأس وصفوف بيانات متعددة. ال`RowFormat.HeadingFormat` تُستخدم المعلمات لتحديد صفوف الرأس التي يجب تكرارها في الصفحات اللاحقة.

## الخطوة 4: حفظ المستند المعدل
أخيرا الولايات المتحدة

  تحتاج إلى حفظ المستند المعدل مع تكرار صفوف الرأس في الصفحات اللاحقة من الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لتكرار الصفوف في الصفحات اللاحقة باستخدام Aspose.Words لـ .NET 

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تكرار صفوف الجدول في الصفحات اللاحقة من مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك تحديد الأسطر التي سيتم تكرارها وفقًا لاحتياجاتك المحددة في مستندات Word الخاصة بك.