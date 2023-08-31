---
title: كرر الصفوف في الصفحات اللاحقة
linktitle: كرر الصفوف في الصفحات اللاحقة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تكرار صفوف الجدول في الصفحات اللاحقة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تكرار صفوف الجدول في الصفحات اللاحقة من مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحديد صفوف لتكرارها في الصفحات اللاحقة من الجدول في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء معالجة الكلمات باستخدام منشئ المستندات والمستندات ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// قم بتهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة الثالثة: بناء الجدول بالصفوف المتكررة
بعد ذلك ، سننشئ جدولًا به صفوف متكررة في الصفحات اللاحقة. استخدم الكود التالي:

```csharp
// بداية الجدول
builder. StartTable();

// تكوين معلمات السطر الأول (خطوط الرأس)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// أدخل الخلية الأولى في الصف الأول
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// أدخل الخلية الثانية من الصف الأول
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// قم بتكوين معلمات الأسطر التالية
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// تكرار لإدراج الخلايا في الصفوف التالية
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

 هنا نستخدم أداة إنشاء المستندات لبناء جدول يحتوي على صفين رأسيين وصفوف بيانات متعددة. ال`RowFormat.HeadingFormat`تُستخدم المعلمات لتحديد صفوف الرأس التي يجب تكرارها في الصفحات اللاحقة.

## الخطوة 4: حفظ المستند المعدل
أخيرا الولايات المتحدة

  تحتاج إلى حفظ المستند المعدل مع تكرار صفوف الرؤوس في الصفحات اللاحقة من الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج لشفرة مصدر لصفوف التكرار في الصفحات اللاحقة باستخدام Aspose.Words for .NET 

```csharp
//المسار إلى دليل المستند الخاص بك
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
في هذا البرنامج التعليمي ، تعلمنا كيفية تكرار صفوف الجدول في الصفحات اللاحقة من مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تحديد الأسطر التي يجب تكرارها وفقًا لاحتياجاتك الخاصة في مستندات Word الخاصة بك.