---
title: تنسيق الجدول والخلية بحدود مختلفة
linktitle: تنسيق الجدول والخلية بحدود مختلفة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتنسيق الجدول والخلية بحدود مختلفة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتنسيق جدول وخلية ذات حدود مختلفة باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تطبيق حدود مخصصة على جدول وخلايا معينة في مستندات Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: ابدأ جدول جديد وأضف خلايا
لبدء إنشاء الجدول ، نستخدم ملف`StartTable()` طريقة منشئ المستندات ، ثم نضيف خلايا إلى الجدول باستخدام الامتداد`InsertCell()` الطريقة ونكتب محتويات الخلايا إلى ملف`Writeln()` طريقة.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// تعيين الحدود للجدول بأكمله.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// تعيين المساحة المتروكة لهذه الخلية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// حدد مساحة خلية مختلفة للخلية الثانية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// امسح تنسيق الخلية من العمليات السابقة.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// قم بإنشاء حدود أكثر سمكًا للخلية الأولى في هذا الصف. سيكون الأمر مختلفا
// بالنسبة للحدود المحددة للجدول.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## الخطوة 4: احفظ المستند

  معدل
أخيرًا احفظ المستند المعدل في ملف. يمكنك اختيار اسم وموقع مناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

تهنئة ! لقد قمت الآن بتنسيق جدول وخلية ذات حدود مختلفة باستخدام Aspose.Words لـ .NET.

### عينة من التعليمات البرمجية المصدر لتنسيق الجدول والخلية ذات الحدود المختلفة باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//عيّن حدود الجدول بأكمله.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// عيّن تظليل الخلية لهذه الخلية.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// حدد تظليل خلية مختلف للخلية الثانية.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// امسح تنسيق الخلية من العمليات السابقة.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// أنشئ حدودًا أكبر للخلية الأولى من هذا الصف. سيكون هذا مختلفا
	// مقارنة بالحدود الموضوعة للجدول.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تنسيق جدول وخلية ذات حدود مختلفة باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تخصيص الجدول وحدود الخلية في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية الاحتياجات الخاصة.