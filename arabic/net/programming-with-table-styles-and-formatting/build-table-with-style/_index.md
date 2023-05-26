---
title: بناء الجدول بأسلوب
linktitle: بناء الجدول بأسلوب
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لبناء طاولة بنمط مخصص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لإنشاء جدول مصمم باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إنشاء جدول بنمط مخصص في مستندات Word باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ مستند Word الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد ومنشئ مستندات
 بعد ذلك ، تحتاج إلى إنشاء مثيل جديد لملف`Document` فئة ومنشئ مستند لذلك المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: ابدأ جدولًا جديدًا وأدخل خلية
 لبدء بناء الجدول ، نستخدم ملف`StartTable()` طريقة إنشاء المستندات ، ثم نقوم بإدخال خلية في الجدول باستخدام الامتداد`InsertCell()` طريقة.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## الخطوة 4: تحديد نمط الجدول
 الآن يمكننا ضبط نمط الجدول باستخدام امتداد`StyleIdentifier` ملكية. في هذا المثال ، نستخدم النمط "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## الخطوة 5: تطبيق خيارات النمط على الجدول
 يمكننا تحديد الخصائص التي يجب تنسيقها بواسطة النمط باستخدام`StyleOptions`خاصية المصفوفة. في هذا المثال ، نطبق الخيارات التالية: "FirstColumn" و "RowBands" و "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## الخطوة 6: ضبط حجم الجدول تلقائيًا
 لضبط حجم المصفوفة تلقائيًا بناءً على محتوياتها ، نستخدم الامتداد`AutoFit()` الطريقة مع`AutoFitBehavior.AutoFitToContents` سلوك.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## الخطوة 7: أضف محتوى إلى الخلايا
 الآن يمكننا إضافة محتوى إلى الخلايا باستخدام امتداد`Writeln()` و`InsertCell()` طرق منشئ الوثيقة. في هذا المثال ، نضيف رؤوس "العنصر" و "الكمية (

كغ) "والبيانات المقابلة.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## الخطوة 8: احفظ المستند المعدل
أخيرًا ، نحفظ المستند المعدل في ملف. يمكنك اختيار اسم وموقع مناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

تهنئة ! لقد قمت الآن ببناء جدول مصمم بشكل مخصص باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لـ Build Table With Style باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// يجب علينا إدراج صف واحد على الأقل أولاً قبل تعيين أي تنسيق للجدول.
	builder.InsertCell();
	// قم بتعيين نمط الجدول المستخدم بناءً على معرف النمط الفريد.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// قم بتطبيق الميزات التي يجب تنسيقها حسب النمط.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء جدول مصمم باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تخصيص نمط الجداول الخاصة بك في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية الاحتياجات الخاصة.