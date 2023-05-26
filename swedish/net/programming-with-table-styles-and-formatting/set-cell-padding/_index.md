---
title: تعيين مساحة الخلية
linktitle: تعيين مساحة الخلية
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتحديد هوامش خلايا الجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين هوامش خلايا الجدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية ضبط الهوامش اليسرى والعلوية واليمنى والسفلية (مساحة) لمحتوى الخلية في جداولك في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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

## الخطوة 4: تعيين هوامش الخلية
 الآن يمكننا تعيين هوامش الخلية باستخدام`SetPaddings()` طريقة`CellFormat` هدف. يتم تعريف الهوامش بالنقاط ومحددة بالترتيب الأيسر والأعلى واليمين والأسفل.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### عينة من التعليمات البرمجية المصدر لـ Set Cell Padding باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// يضبط مقدار المسافة (بالنقاط) لإضافتها إلى اليسار / أعلى / يمين / أسفل محتويات الخلية.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين هوامش خلية جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة ضبط هوامش الخلية لإنشاء مسافات إلى اليسار ، وأعلى ، ويمين ، وأسفل المحتوى في جداولك في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص تنسيق الجداول حسب احتياجاتك الخاصة.