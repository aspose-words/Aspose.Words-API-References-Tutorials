---
title: إنشاء تذييل الرأس
linktitle: إنشاء تذييل الرأس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء رؤوس الصفحات وتذييلاتها في مستندات Word باستخدام Aspose.Words for .NET. تخصيص الرؤوس والتذييلات لكل صفحة.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/create-header-footer/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح التعليمات البرمجية المصدر C # التالية لإنشاء رؤوس وتذييلات باستخدام Aspose.Words لوظائف .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث سيتم حفظ المستند المحرر.

## الخطوة 2: قم بإنشاء مستند ومولد مستندات

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 هنا نقوم بإنشاء مثيل لـ`Document` فئة ومثيل`DocumentBuilder` فئة تسمح لنا بمعالجة المستند وإضافة عناصر.

## الخطوة 3: تعيين معلمات الصفحة والعنوان الأول

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// حدد ما إذا كنا نريد أن تختلف رؤوس / تذييلات الصفحة الأولى عن الصفحات الأخرى.
// يمكنك أيضًا استخدام خاصية PageSetup.OddAndEvenPagesHeaderFooter لتحديدها
// رؤوس / تذييلات مختلفة للصفحات الفردية والزوجية.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

نقوم بتعيين معلمات الصفحة ، بما في ذلك مسافة الرأس ، ثم ننتقل إلى العنوان الرئيسي (`HeaderPrimary`). نستخدم منشئ المستندات لإضافة نص وتنسيق العنوان.

## الخطوة 4: أدخل صورة ونصًا في العنوان الرئيسي

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

نستخدم منشئ المستندات لإدراج صورة في الزاوية اليسرى العلوية من الرأس الرئيسي ، ثم نضيف بعض النص المحاذي لليمين.

## الخطوة 5: قم بإدراج جدول في التذييل الرئيسي

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## الخطوة 6: إضافة صفحة جديدة وتعيين الرؤوس / التذييلات

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//لا يحتاج هذا القسم إلى رأس / تذييل مختلف للصفحة الأولى ، نحتاج فقط إلى صفحة عنوان واحدة في المستند ،
// وقد تم بالفعل تحديد رأس / تذييل الصفحة في القسم السابق.
pageSetup.DifferentFirstPageHeaderFooter = false;

// يعرض هذا القسم رؤوس / تذييلات القسم السابق افتراضيًا ، استدعاء currentSection.HeadersFooters.LinkToPrevious (خطأ) لكسر هذا الرابط ،
// يختلف عرض الصفحة بالنسبة للقسم الجديد ، لذلك نحتاج إلى تعيين عروض خلايا مختلفة لجدول تذييل الصفحة.
currentSection.HeadersFooters.LinkToPrevious(false);

// إذا أردنا استخدام الرؤوس / التذييلات الموجودة بالفعل لهذا القسم ،
// ولكن مع بعض التغييرات الطفيفة ، قد يكون من المنطقي نسخ الرؤوس / التذييلات
// من القسم السابق وتطبيق التغييرات اللازمة حيث نريدها.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// احفظ المستند
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 نضيف فاصل صفحة وفاصل مقطعي لإنشاء صفحة جديدة حيث ستكون الرؤوس / التذييلات الأولية مرئية. قمنا بتعيين معلمات القسم الجديد ، ثم نستخدم الامتداد`CopyHeadersFootersFromPreviousSection`طريقة لنسخ الرؤوس / التذييلات من القسم السابق. أخيرًا ، قمنا بتعيين عرض الخلية المناسب لجدول التذييل الرئيسي وحفظنا المستند.

### مثال على كود المصدر لإنشاء الرؤوس والتذييلات باستخدام Aspose.Words for .NET

```csharp
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	Section currentSection = builder.CurrentSection;
	PageSetup pageSetup = currentSection.PageSetup;
	// حدد ما إذا كنا نريد أن تختلف رؤوس / تذييلات الصفحة الأولى عن الصفحات الأخرى.
	// يمكنك أيضًا استخدام خاصية PageSetup.OddAndEvenPagesHeaderFooter لتحديدها
	// رؤوس / تذييلات مختلفة للصفحات الفردية والزوجية.
	pageSetup.DifferentFirstPageHeaderFooter = true;
	pageSetup.HeaderDistance = 20;

	builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.Font.Size = 14;

	builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

	pageSetup.HeaderDistance = 20;
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

	// أدخل صورة موضوعة في الزاوية العلوية / اليسرى من الرأس.
	// تم ضبط المسافة من الحواف العلوية / اليسرى للصفحة على 10 نقاط.
	builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
		RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.Write("Aspose.Words Header/Footer Creation Primer.");

	builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

	// نستخدم جدولاً يحتوي على خليتين لعمل جزء واحد من النص على السطر (مع ترقيم الصفحات).
	// تتم محاذاة إلى اليسار ، ويتم محاذاة الجزء الآخر من النص (مع حقوق النشر) إلى اليمين.
	builder.StartTable();

	builder.CellFormat.ClearFormatting();

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

	// يستخدم حقلي PAGE و NUMPAGES لحساب تلقائي لرقم الصفحة الحالية والعديد من الصفحات.
	builder.Write("Page ");
	builder.InsertField("PAGE", "");
	builder.Write(" of ");
	builder.InsertField("NUMPAGES", "");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.EndRow();
	builder.EndTable();

	builder.MoveToDocumentEnd();

	// قم بعمل فاصل صفحة لإنشاء صفحة ثانية تظهر عليها الرؤوس / التذييلات الأساسية.
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertBreak(BreakType.SectionBreakNewPage);

	currentSection = builder.CurrentSection;
	pageSetup = currentSection.PageSetup;
	pageSetup.Orientation = Orientation.Landscape;
	//لا يحتاج هذا القسم إلى رأس / تذييل مختلف للصفحة الأولى ، فنحن نحتاج فقط إلى صفحة عنوان واحدة في المستند ،
	// وقد تم بالفعل تحديد رأس / تذييل الصفحة في القسم السابق.
	pageSetup.DifferentFirstPageHeaderFooter = false;

	// يعرض هذا القسم الرؤوس / التذييلات من القسم السابق
	// بشكل افتراضي ، قم باستدعاء currentSection.HeadersFooters.LinkToPrevious (false) لإلغاء عرض هذه الصفحة
	// يختلف عن القسم الجديد ، وبالتالي نحتاج إلى تعيين عروض خلايا مختلفة لجدول تذييل.
	currentSection.HeadersFooters.LinkToPrevious(false);

	// إذا أردنا استخدام مجموعة الرأس / التذييل الموجودة بالفعل لهذا القسم.
	// ولكن مع بعض التعديلات الطفيفة ، قد يكون من المناسب نسخ الرؤوس / التذييلات
	// من القسم السابق وتطبيق التعديلات اللازمة حيث نريدها.
	CopyHeadersFootersFromPreviousSection(currentSection);

	HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

	Row row = primaryFooter.Tables[0].FirstRow;
	row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
	row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```
