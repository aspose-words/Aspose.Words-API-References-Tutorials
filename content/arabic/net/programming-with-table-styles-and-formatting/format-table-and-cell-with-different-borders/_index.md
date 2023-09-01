---
title: تنسيق الجدول والخلية بحدود مختلفة
linktitle: تنسيق الجدول والخلية بحدود مختلفة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتنسيق الجدول والخلية بحدود مختلفة باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتنسيق جدول وخلية بحدود مختلفة باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية تطبيق حدود مخصصة على جدول وخلايا معينة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي تريد حفظ مستند Word الذي تم تحريره فيه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد ومنشئ المستندات
 بعد ذلك، تحتاج إلى إنشاء مثيل جديد لـ`Document` فئة ومنشئ مستند لتلك الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: ابدأ جدولاً جديدًا وأضف الخلايا
للبدء في إنشاء الجدول، نستخدم`StartTable()` طريقة منشئ المستندات، ثم نضيف خلايا إلى الجدول باستخدام`InsertCell()` الطريقة ونكتب محتويات الخلايا باستخدام`Writeln()` طريقة.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// تعيين حدود للجدول بأكمله.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// تعيين الحشو لهذه الخلية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// حدد حشوة خلية مختلفة للخلية الثانية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// مسح تنسيق الخلية من العمليات السابقة.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// قم بإنشاء حدود أكثر سمكًا للخلية الأولى في هذا الصف. سيكون مختلفا
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
أخيرًا احفظ المستند المعدل في ملف. يمكنك اختيار الاسم والموقع المناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

تهنئة ! لقد قمت الآن بتنسيق جدول وخلية بحدود مختلفة باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لتنسيق الجدول والخلية بحدود مختلفة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//تعيين الحدود للجدول بأكمله.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// قم بتعيين تظليل الخلية لهذه الخلية.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// حدد تظليلًا مختلفًا للخلية الثانية.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// امسح تنسيق الخلية من العمليات السابقة.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// قم بإنشاء حدود أكبر للخلية الأولى من هذا الصف. هذا سيكون مختلفا
	// مقارنة بالحدود المحددة للجدول.
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
في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق جدول وخلية بحدود مختلفة باستخدام Aspose.Words for .NET. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك بسهولة تخصيص حدود الجدول والخلايا في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية الاحتياجات المحددة.