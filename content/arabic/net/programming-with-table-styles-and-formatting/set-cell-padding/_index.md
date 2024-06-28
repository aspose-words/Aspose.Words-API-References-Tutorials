---
title: تعيين حشوة الخلية
linktitle: تعيين حشوة الخلية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد هوامش خلايا الجدول باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتعيين هوامش خلايا الجدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية ضبط الهوامش اليسرى والعليا واليمنى والسفلية (المسافة) لمحتوى الخلية في الجداول الخاصة بك في مستندات Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: ابدأ جدولاً جديدًا وأضف خلية
للبدء في إنشاء الجدول، نستخدم`StartTable()` طريقة منشئ المستند، ثم نضيف خلية إلى الجدول باستخدام`InsertCell()` طريقة.

```csharp
builder. StartTable();
builder. InsertCell();
```

## الخطوة 4: تعيين هوامش الخلية
 الآن يمكننا ضبط هوامش الخلية باستخدام`SetPaddings()` طريقة`CellFormat` هدف. يتم تعريف الهوامش بالنقاط ويتم تحديدها بالترتيب لليسار والأعلى واليمين والأسفل.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## الخطوة 5: إضافة محتوى إلى الخلية
 ثم يمكننا إضافة محتوى إلى الخلية باستخدام أداة إنشاء المستندات`Writeln()` طريقة.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## الخطوة 6: قم بإنهاء الجدول وحفظ المستند
 وأخيرا، انتهينا من إنشاء الجدول باستخدام`EndRow()` طريقة و`EndTable()`، ثم نقوم بحفظ المستند المعدل في ملف.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### نموذج التعليمات البرمجية المصدر لـ Set Cell Padding باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// يضبط مقدار المساحة (بالنقاط) المراد إضافتها إلى يسار/أعلى/يمين/أسفل محتويات الخلية.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين هوامش خلية الجدول باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة، يمكنك بسهولة ضبط هوامش الخلايا لإنشاء مسافات على يسار المحتوى وأعلىه ويمينه وأسفله في جداولك في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تخصيص تنسيق جداولك وفقًا لاحتياجاتك المحددة.