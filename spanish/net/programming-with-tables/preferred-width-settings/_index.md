---
title: إعدادات العرض المفضلة
linktitle: إعدادات العرض المفضلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين عروض خلية الجدول المفضلة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/preferred-width-settings/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تعيين إعدادات العرض المفضلة لخلايا الجدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحديد عروض مختلفة مفضلة لخلايا الجدول في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء العمل مع منشئ المستندات والمستندات ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// قم بتهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء الجدول بالعروض المفضلة
بعد ذلك ، سنقوم ببناء جدول بثلاث خلايا لها عروض مختلفة مفضلة. استخدم الكود التالي:

```csharp
// بداية الجدول
builder. StartTable();

// أدخل خلية ذات حجم مطلق
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// أدخل خلية ذات حجم نسبي (بالنسبة المئوية)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// أدخل خلية ذات حجم تلقائي
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// نهاية الجدول
builder. EndTable();
```

هنا نستخدم منشئ المستندات لبناء جدول بثلاث خلايا. للخلية الأولى عرض مفضل يبلغ 40 نقطة ، والخلية الثانية لها عرض مفضل بنسبة 20٪ من عرض الجدول ، والخلية الثالثة لها عرض مفضل تلقائي يتم ضبطه

  حسب المساحة المتوفرة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل بإعدادات العرض المفضلة المحددة لخلايا الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج رمز مصدر لإعدادات العرض المفضلة باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// أدخل صف جدول مكون من ثلاث خلايا لها عروض مختلفة مفضلة.
	builder.StartTable();
	// أدخل خلية ذات حجم مطلق.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// أدخل خلية ذات حجم نسبي (نسبة مئوية).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// أدخل خلية بحجم تلقائي.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين إعدادات العرض المفضلة لخلايا الجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تخصيص عرض خلايا الجدول وفقًا لاحتياجاتك المحددة في مستندات Word الخاصة بك.