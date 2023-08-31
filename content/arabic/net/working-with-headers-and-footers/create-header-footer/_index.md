---
title: إنشاء تذييل الرأس
linktitle: إنشاء تذييل الرأس
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء الرؤوس والتذييلات في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET. تخصيص الرؤوس والتذييلات لكل صفحة.
type: docs
weight: 10
url: /ar/net/working-with-headers-and-footers/create-header-footer/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# التالية لإنشاء الرؤوس والتذييلات باستخدام Aspose.Words لوظيفة .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: قم بتعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث سيتم حفظ المستند المحرر.

## الخطوة 2: إنشاء مستند ومولد المستندات

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 هنا نقوم بإنشاء مثيل لـ`Document` فئة ومثال على`DocumentBuilder` فئة والتي سوف تسمح لنا بمعالجة الوثيقة وإضافة عناصر.

## الخطوة 3: تعيين معلمات الصفحة والرأس الأول

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// حدد ما إذا كنا نريد أن تكون رؤوس/تذييلات الصفحة الأولى مختلفة عن الصفحات الأخرى.
// يمكنك أيضًا استخدام الخاصية PageSetup.OddAndEvenPagesHeaderFooter للتحديد
// رؤوس/تذييلات مختلفة للصفحات الفردية والزوجية.
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

نقوم بتعيين معلمات الصفحة، بما في ذلك مسافة الرأس، ثم ننتقل إلى الرأس الرئيسي (`HeaderPrimary`). نستخدم منشئ المستندات لإضافة نص وتنسيق الرأس.

## الخطوة 4: أدخل صورة ونصًا في الرأس الرئيسي

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

نستخدم منشئ المستندات لإدراج صورة في الزاوية اليسرى العليا من الرأس الرئيسي، ثم نضيف بعض النص بمحاذاة إلى اليمين.

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

## الخطوة 6: أضف صفحة جديدة وقم بتعيين الرؤوس/التذييلات

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// لا يحتاج هذا القسم إلى رأس/تذييل مختلف للصفحة الأولى، نحتاج فقط إلى صفحة عنوان واحدة في المستند،
// وقد تم بالفعل تحديد رأس/تذييل هذه الصفحة في القسم السابق.
pageSetup.DifferentFirstPageHeaderFooter = false;

// يعرض هذا القسم رؤوس/تذييلات القسم السابق بشكل افتراضي، اتصل بـcurrentSection.HeadersFooters.LinkToPrevious(false) لقطع هذا الارتباط،
// يختلف عرض الصفحة بالنسبة للقسم الجديد، لذلك نحتاج إلى تعيين عروض خلايا مختلفة لجدول التذييل.
currentSection.HeadersFooters.LinkToPrevious(false);

//إذا أردنا استخدام الرؤوس/التذييلات الموجودة بالفعل لهذا القسم،
// ولكن مع بعض التغييرات الطفيفة، قد يكون من المنطقي نسخ الرؤوس/التذييلات
// من القسم السابق وقم بتطبيق التغييرات اللازمة حيث نريدها.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// احفظ المستند
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 نضيف فاصل صفحة وفاصل مقطعي لإنشاء صفحة جديدة حيث ستكون الرؤوس/التذييلات الأساسية مرئية. نقوم بتعيين المعلمات للقسم الجديد، ثم نستخدم`CopyHeadersFootersFromPreviousSection` طريقة لنسخ الرؤوس والتذييلات من القسم السابق. أخيرًا، قمنا بتعيين عرض الخلايا المناسب لجدول التذييل الرئيسي وحفظ المستند.

### مثال على التعليمات البرمجية المصدر لإنشاء الرؤوس والتذييلات باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// حدد ما إذا كنا نريد أن تكون رؤوس/تذييلات الصفحة الأولى مختلفة عن الصفحات الأخرى.
// يمكنك أيضًا استخدام خاصية PageSetup.OddAndEvenPagesHeaderFooter للتحديد
// رؤوس/تذييلات مختلفة للصفحات الفردية والزوجية.
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

// قم بإدراج صورة موضوعة في الزاوية العلوية/اليسرى من الرأس.
// يتم ضبط المسافة من الحواف العلوية/اليسرى للصفحة على 10 نقاط.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//نستخدم جدولاً يحتوي على خليتين لإنشاء جزء واحد من النص على السطر (مع ترقيم الصفحات).
// تتم محاذاته إلى اليسار، ومحاذاة الجزء الآخر من النص (مع حقوق الطبع والنشر) إلى اليمين.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// ويستخدم حقول PAGE وNUMPAGES لحساب رقم الصفحة الحالية والعديد من الصفحات تلقائيًا.
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

// قم بعمل فاصل صفحات لإنشاء صفحة ثانية تظهر عليها الرؤوس والتذييلات الأساسية.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// لا يحتاج هذا القسم إلى رأس/تذييل مختلف للصفحة الأولى، فنحن نحتاج فقط إلى صفحة عنوان واحدة في المستند،
// وقد تم بالفعل تحديد رأس/تذييل هذه الصفحة في القسم السابق.
pageSetup.DifferentFirstPageHeaderFooter = false;

// يعرض هذا القسم الرؤوس/التذييلات من القسم السابق
// بشكل افتراضي، قم باستدعاء currentSection.HeadersFooters.LinkToPrevious(false) لإلغاء عرض الصفحة هذا
// يختلف بالنسبة للقسم الجديد، وبالتالي نحتاج إلى تعيين عروض مختلفة للخلايا لجدول التذييل.
currentSection.HeadersFooters.LinkToPrevious(false);

// إذا أردنا استخدام مجموعة الرأس/التذييل الموجودة بالفعل لهذا القسم.
// ولكن مع بعض التعديلات الطفيفة، قد يكون من المناسب نسخ الرؤوس/التذييلات
//من القسم السابق وتطبيق التعديلات اللازمة حيث نريدها.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### الأسئلة الشائعة

#### س: كيف يمكنني إضافة رأس إلى مستندي في Aspose.Words؟

 ج: لإضافة رأس إلى مستندك في Aspose.Words، يمكنك استخدام الملف`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` طريقة. تضيف هذه الطريقة عنوانًا أساسيًا إلى القسم الأول من المستند.

#### س: كيف يمكنني إضافة تذييل إلى مستندي في Aspose.Words؟

 ج: لإضافة تذييل إلى مستندك في Aspose.Words، يمكنك استخدام الملف`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` طريقة. تضيف هذه الطريقة تذييلًا أساسيًا إلى القسم الأول من المستند.

#### س: كيف يمكنني إضافة نص إلى رأس الصفحة أو تذييل الصفحة في Aspose.Words؟

 ج: لإضافة نص إلى رأس الصفحة أو تذييلها في Aspose.Words، يمكنك استخدام`HeaderFooter.Paragraphs` للحصول على مجموعة الفقرات من الرأس أو التذييل، ثم قم بإضافة فقرة تحتوي على النص الخاص بك إلى هذه المجموعة باستخدام الخاصية`ParagraphCollection.Add` طريقة.

#### س: هل يمكنني تخصيص محتوى الرأس أو التذييل باستخدام الصور وأرقام الصفحات في Aspose.Words؟

ج: نعم، يمكنك تخصيص محتوى الرأس أو التذييل باستخدام الصور وأرقام الصفحات في Aspose.Words. يمكنك استخدام كائنات مثل`Shape` لإضافة الصور والكائنات مثل`Field` لإضافة أرقام الصفحات إلى رأس الصفحة أو تذييلها.

#### س: هل يمكنني تغيير خط النص وحجمه ولونه في رأس الصفحة أو تذييلها في Aspose.Words؟

 ج: نعم، يمكنك تغيير خط النص وحجمه ولونه في رأس الصفحة أو تذييل الصفحة في Aspose.Words. يمكنك الوصول إلى خصائص تنسيق النص مثل`Font` لتغيير الخط،`Size` لضبط الحجم، و`Color` لتعيين لون النص.