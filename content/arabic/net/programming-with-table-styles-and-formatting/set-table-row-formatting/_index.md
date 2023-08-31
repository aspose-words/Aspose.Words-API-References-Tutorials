---
title: تعيين تنسيق صف الجدول
linktitle: تعيين تنسيق صف الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد تنسيق صف الجدول باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتعيين تنسيق صف الجدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية ضبط الارتفاع وحشوات صف الجدول في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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
Table table = builder. StartTable();
builder. InsertCell();
```

## الخطوة 4: تحديد تنسيق الخط
 يمكننا الآن ضبط تنسيق الصف عن طريق الوصول إلى ملف`RowFormat` كائن من`DocumentBuilder` هدف. يمكننا ضبط ارتفاع الخط والهوامش (الحشوات) باستخدام الخصائص المقابلة.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## الخطوة 5: تعيين هوامش الجدول
 بعد ذلك، يمكننا ضبط حشوات الجدول عن طريق الوصول إلى الخصائص المقابلة للملف`Table` هدف. سيتم تطبيق هذه الهوامش على كافة صفوف الجدول.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## الخطوة 6: إضافة محتوى إلى الصف
 وأخيرًا، يمكننا إضافة محتوى إلى السطر باستخدام أداة إنشاء المستندات`Writeln()` طريقة.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## الخطوة 7: قم بإنهاء الجدول وحفظ المستند
في

 في النهاية، ننتهي من إنشاء الجدول باستخدام`EndRow()` و`EndTable()` الطريقة، ثم نقوم بحفظ المستند المعدل إلى ملف.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لتعيين تنسيق صف الجدول باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// يتم تعيين خصائص التنسيق هذه على الجدول ويتم تطبيقها على كافة الصفوف في الجدول.
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
في هذا البرنامج التعليمي، تعلمنا كيفية ضبط تنسيق صف الجدول باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل خطوة بخطوة، يمكنك بسهولة ضبط ارتفاع صف الجدول والهوامش في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك المحددة.