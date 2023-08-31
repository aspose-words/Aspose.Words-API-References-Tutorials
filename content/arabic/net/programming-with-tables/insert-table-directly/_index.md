---
title: إدراج الجدول مباشرة
linktitle: إدراج الجدول مباشرة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج جدول مباشرةً في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/insert-table-directly/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية إدراج جدول مباشرةً في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على إدراج الجداول مباشرة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند والجدول
لبدء معالجة الكلمات باستخدام المصفوفة، نحتاج إلى إنشاء مستند جديد وتهيئة المصفوفة. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

//قم بإنشاء المصفوفة
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: بناء المصفوفة
بعد ذلك، سنقوم ببناء الجدول بإضافة صفوف وخلايا. استخدم الكود التالي كمثال:

```csharp
// إنشاء الصف الأول
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// إنشاء الخلية الأولى
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// قم بتكرار الخلية للخلية الثانية في الصف
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 هنا نقوم بإنشاء صف مع`AllowBreakAcrossPages` خاصية تعيين ل`true` للسماح بفصل الصفحات بين الصفوف. نقوم بعد ذلك بإنشاء خلية ذات خلفية ملونة وعرض ثابت ومحتوى نصي محدد. ثم نقوم بتكرار هذه الخلية لإنشاء الخلية الثانية في الصف.

## الخطوة 4: جدول الاحتواء التلقائي
يمكننا تطبيق التعديلات التلقائية على الجدول لتنسيقه بشكل صحيح. استخدم الكود التالي:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

يطبق سطر التعليمات البرمجية هذا احتواءًا تلقائيًا استنادًا إلى عرض الأعمدة الثابتة.

## الخطوة 5: تسجيل

  وثيقة معدلة
أخيرًا، نحتاج إلى حفظ المستند المعدل مع إدراج الجدول مباشرةً. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لإدراج جدول مباشرة باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// نبدأ بإنشاء كائن الجدول. لاحظ أنه يجب علينا تمرير كائن المستند
	//إلى منشئ كل عقدة. وذلك لأن كل عقدة نقوم بإنشائها يجب أن تنتمي
	// إلى بعض الوثيقة.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// هنا يمكننا الاتصال بـ EnsureMinimum لإنشاء الصفوف والخلايا لنا. يتم استخدام هذه الطريقة
	// للتأكد من صحة العقدة المحددة. في هذه الحالة، يجب أن يحتوي الجدول الصالح على صف واحد وخلية واحدة على الأقل.
	// وبدلاً من ذلك، سنتولى إنشاء الصف والجدول بأنفسنا.
	// ستكون هذه أفضل طريقة للقيام بذلك إذا كنا نقوم بإنشاء جدول داخل خوارزمية.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// يمكننا الآن تطبيق أي إعدادات ملائمة تلقائية.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// ثم نكرر العملية مع الخلايا والصفوف الأخرى في الجدول.
	// يمكننا أيضًا تسريع الأمور عن طريق استنساخ الخلايا والصفوف الموجودة.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إدراج جدول مباشرةً في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك إدراج الجداول مباشرة في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة إنشاء الجداول وتخصيصها وفقًا لاحتياجاتك المحددة.