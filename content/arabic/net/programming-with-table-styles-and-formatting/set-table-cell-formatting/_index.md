---
title: تعيين تنسيق خلايا الجدول
linktitle: تعيين تنسيق خلايا الجدول
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لإعداد تنسيق خلايا الجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتحديد تنسيق خلية الجدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية ضبط العرض والهوامش (الحشوات) لخلية في جداول مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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

## الخطوة 3: ابدأ جدول جديد وأضف خلية
لبدء إنشاء الجدول ، نستخدم ملف`StartTable()` طريقة منشئ المستند ، ثم نضيف خلية إلى الجدول باستخدام الامتداد`InsertCell()` طريقة.

```csharp
builder. StartTable();
builder. InsertCell();
```

## الخطوة 4: تعيين تنسيق الخلية
 الآن يمكننا ضبط تنسيق الخلية عن طريق الوصول إلى ملف`CellFormat` كائن`DocumentBuilder` هدف. يمكننا ضبط عرض الخلية والهوامش (الحشوات) باستخدام الخصائص المقابلة.

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## الخطوة 5: أضف محتوى إلى الخلية
 ثم يمكننا إضافة محتوى إلى الخلية باستخدام منشئ المستندات`Writeln()` طريقة.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## الخطوة السادسة: قم بإنهاء الجدول وحفظ المستند
 أخيرًا ، ننتهي من إنشاء الجدول باستخدام`EndRow()` طريقة و`EndTable()`، ثم نقوم بحفظ المستند المعدل في ملف.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لـ Set Table Cell Formatting باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين تنسيق خلية جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة ضبط عرض وهوامش خلية في الجداول الخاصة بك في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك الخاصة.