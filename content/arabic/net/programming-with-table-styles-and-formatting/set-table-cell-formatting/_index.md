---
title: ضبط تنسيق خلايا الجدول
linktitle: ضبط تنسيق خلايا الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد تنسيق خلايا الجدول باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتحديد تنسيق خلية الجدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية ضبط العرض والهوامش (المساحات) للخلية في جداول مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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

## الخطوة 4: ضبط تنسيق الخلية
 يمكننا الآن ضبط تنسيق الخلية عن طريق الوصول إلى ملف`CellFormat` كائن من`DocumentBuilder` هدف. يمكننا ضبط عرض الخلية والهوامش (الحشوات) باستخدام الخصائص المقابلة.

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لتعيين تنسيق خلايا الجدول باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
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
في هذا البرنامج التعليمي، تعلمنا كيفية ضبط تنسيق خلية الجدول باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة، يمكنك بسهولة ضبط عرض وهوامش الخلية في جداولك في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك المحددة.