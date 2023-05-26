---
title: تعيين تنسيق صف الجدول
linktitle: تعيين تنسيق صف الجدول
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإعداد تنسيق صف الجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين تنسيق صف الجدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية ضبط الارتفاع والحشو لصف الجدول في مستندات Word باستخدام Aspose.Words for .NET.

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
Table table = builder. StartTable();
builder. InsertCell();
```

## الخطوة 4: تحديد تنسيق الخط
 الآن يمكننا ضبط تنسيق الصف من خلال الوصول إلى ملف`RowFormat` كائن`DocumentBuilder` هدف. يمكننا ضبط ارتفاع الخط والهوامش (الحشوات) باستخدام الخصائص المقابلة.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## الخطوة 5: تعيين هوامش الجدول
 بعد ذلك ، يمكننا ضبط حشوات الجدول من خلال الوصول إلى الخصائص المقابلة لـ`Table` هدف. سيتم تطبيق هذه الهوامش على جميع صفوف الجدول.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## الخطوة 6: أضف محتوى إلى الصف
 أخيرًا ، يمكننا إضافة محتوى إلى السطر باستخدام منشئ المستندات`Writeln()` طريقة.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## الخطوة 7: قم بإنهاء الجدول وحفظ المستند
في

 النهاية ، ننتهي من إنشاء الجدول باستخدام`EndRow()` و`EndTable()` الطريقة ، ثم نقوم بحفظ المستند المعدل في ملف.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لـ Set Table Row Formatting باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// يتم تعيين خصائص التنسيق هذه في الجدول ويتم تطبيقها على جميع الصفوف في الجدول.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين تنسيق صف الجدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة ضبط ارتفاع صف الجدول والهوامش في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك الخاصة.