---
title: جدول منسق
linktitle: جدول منسق
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول منسق في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/formatted-table/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إنشاء جدول منسق في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من إنشاء جداول بتنسيق مخصص في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء بناء الجدول المنسق ، نحتاج إلى إنشاء مستند جديد وتهيئة منشئ المستندات. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وتهيئة منشئ المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء الجدول المنسق
بعد ذلك ، سنقوم ببناء الجدول المنسق باستخدام الطرق التي يوفرها منشئ المستندات. استخدم الكود التالي:

```csharp
// ابدأ بناء المصفوفة
Table table = builder. StartTable();

// بناء صف رأس الجدول
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// بناء الجسم المصفوفة
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// نهاية بناء المصفوفة
builder. EndTable();
```

 هنا نستخدم منشئ المستندات لبناء الجدول خطوة بخطوة. نبدأ بالاتصال`StartTable()` لتهيئة الجدول. ثم نستخدم`InsertCell()` لإدراج الخلايا و`Write()` لإضافة محتوى إلى كل خلية. نستخدم أيضًا خصائص تنسيق مختلفة لتحديد تنسيق صفوف الجدول والخلايا والنص.

## الخطوة 4: احفظ المستند
أخيرًا ، نحتاج إلى حفظ المستند الذي يحتوي على الجدول المنسق. استخدم الكود التالي:

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر للجدول المنسق باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// يجب تطبيق التنسيق الواسع للجدول بعد وجود صف واحد على الأقل في الجدول.
	table.LeftIndent = 20.0;
	// عيّن الارتفاع وحدد قاعدة الارتفاع لصف الرأس.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// لا نحتاج إلى تحديد عرض هذه الخلية لأنها موروثة من الخلية السابقة.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// إعادة تعيين الارتفاع وتحديد قاعدة ارتفاع مختلفة لجسم الجدول.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// إعادة تعيين تنسيق الخط.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء جدول منسق في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إنشاء جداول مخصصة بتنسيق محدد في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تقديم بياناتك وتنظيمها بطريقة جذابة بصريًا ومنظمة.