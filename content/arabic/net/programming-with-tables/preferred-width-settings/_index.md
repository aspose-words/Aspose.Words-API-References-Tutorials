---
title: إعدادات العرض المفضلة
linktitle: إعدادات العرض المفضلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين عرض خلايا الجدول المفضل في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/preferred-width-settings/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية تعيين إعدادات العرض المفضلة لخلايا الجدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على تحديد عروض مفضلة مختلفة لخلايا الجدول في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستندات
لبدء معالجة الكلمات باستخدام منشئ المستندات والمستندات، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// تهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: بناء الجدول بالعروض المفضلة
بعد ذلك، سنقوم بإنشاء جدول يحتوي على ثلاث خلايا ذات عروض مفضلة مختلفة. استخدم الكود التالي:

```csharp
// بداية الجدول
builder. StartTable();

// أدخل خلية بالحجم المطلق
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// إدراج خلية ذات حجم نسبي (بالنسبة المئوية)
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

نستخدم هنا أداة إنشاء المستندات لإنشاء جدول بثلاث خلايا. الخلية الأولى لها العرض المفضل 40 نقطة، والخلية الثانية لها العرض المفضل 20% من عرض الجدول، والخلية الثالثة لها العرض المفضل التلقائي الذي يضبط

  اعتمادا على المساحة المتاحة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بإعدادات العرض المفضلة المحددة لخلايا الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لإعدادات العرض المفضلة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// قم بإدراج صف جدول يتكون من ثلاث خلايا ذات عروض مفضلة مختلفة.
	builder.StartTable();
	// أدخل خلية ذات حجم مطلق.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// قم بإدراج خلية ذات حجم نسبي (نسبة مئوية).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// أدخل خلية ذات حجم تلقائي.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين إعدادات العرض المفضلة لخلايا الجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك تخصيص عرض خلايا الجدول الخاص بك وفقًا لاحتياجاتك المحددة في مستندات Word الخاصة بك.