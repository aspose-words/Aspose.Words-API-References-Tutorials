---
title: أدخل الجدول مباشرة
linktitle: أدخل الجدول مباشرة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج جدول مباشرة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-directly/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إدراج جدول مباشرة في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من إدراج الجداول مباشرةً في مستندات Word برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند والجدول
لبدء العمل مع المصفوفة ، نحتاج إلى إنشاء مستند جديد وتهيئة المصفوفة. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// قم بإنشاء المصفوفة
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء المصفوفة
بعد ذلك ، سنبني الجدول بإضافة صفوف وخلايا. استخدم الكود التالي كمثال:

```csharp
// قم بإنشاء الصف الأول
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// قم بإنشاء الخلية الأولى
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

 هنا ننشئ صفًا بامتداد`AllowBreakAcrossPages` تعيين الخاصية على`true` للسماح بفصل الصفحات بين الصفوف. نقوم بعد ذلك بإنشاء خلية ذات خلفية ملونة وعرض ثابت ومحتوى نصي محدد. ثم نكرر هذه الخلية لإنشاء الخلية الثانية في الصف.

## الخطوة 4: جدول ملاءمة تلقائي
يمكننا تطبيق تعديلات تلقائية على الجدول لتنسيقه بشكل صحيح. استخدم الكود التالي:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

يطبق سطر التعليمات البرمجية هذا احتواءًا تلقائيًا استنادًا إلى عرض العمود الثابت.

## الخطوة 5: تسجيل ملف

  وثيقة معدلة
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع إدراج الجدول مباشرةً. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Insert Table مباشرة باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// نبدأ بإنشاء كائن الجدول. لاحظ أنه يجب علينا تمرير كائن المستند
	//منشئ كل عقدة. هذا لأن كل عقدة نقوم بإنشائها يجب أن تنتمي
	// لبعض الوثائق.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// هنا يمكننا أن نطلق على "ضمان الحد الأدنى" لإنشاء الصفوف والخلايا لنا. تستخدم هذه الطريقة
	// للتأكد من أن العقدة المحددة صالحة. في هذه الحالة ، يجب أن يحتوي الجدول الصالح على صف واحد وخلية واحدة على الأقل.
	// بدلاً من ذلك ، سنتعامل مع إنشاء الصف والجدول بأنفسنا.
	// ستكون هذه أفضل طريقة للقيام بذلك إذا كنا ننشئ جدولًا داخل خوارزمية.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// يمكننا الآن تطبيق أي إعدادات احتواء تلقائي.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// ثم نكرر العملية للخلايا والصفوف الأخرى في الجدول.
	// يمكننا أيضًا تسريع الأمور عن طريق استنساخ الخلايا والصفوف الموجودة.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إدراج جدول مباشرة في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ رمز C # المقدم ، يمكنك إدراج الجداول مباشرةً في مستندات Word برمجيًا. تتيح لك هذه الميزة إنشاء الجداول وتخصيصها وفقًا لاحتياجاتك الخاصة.