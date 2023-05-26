---
title: تطبيق تنسيق الصفوف
linktitle: تطبيق تنسيق الصفوف
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتطبيق تنسيق الصفوف على جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتطبيق تنسيق الصف على جدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، سيكون لديك فهم واضح لكيفية تنسيق صفوف الجدول في مستندات Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: ابدأ لوحة جديدة
 لتطبيق تنسيق الصفوف ، يجب أن نبدأ أولاً في جدول جديد باستخدام`StartTable()` طريقة منشئ الوثيقة.

```csharp
Table table = builder. StartTable();
```

## الخطوة 4: أدخل خلية وانتقل إلى تنسيق الصف
يمكننا الآن إدراج خلية في الجدول والوصول إلى تنسيق الصف لتلك الخلية باستخدام منشئ المستندات`InsertCell()` و`RowFormat` طُرق.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## الخطوة 5: ضبط ارتفاع الصف
 لتعيين ارتفاع الصف ، نستخدم`Height` و`HeightRule` خصائص تنسيق الصف. في هذا المثال ، قمنا بتعيين ارتفاع صف بمقدار 100 نقطة واستخدمنا`Exactly` قاعدة.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## الخطوة 6: تحديد تنسيق الجدول
 يمكن تعيين بعض خصائص التنسيق في الجدول نفسه وتطبيقها على جميع صفوف الجدول. في هذا المثال ، قمنا بتعيين خصائص هامش الجدول باستخدام`LeftPadding`, `RightPadding`, `TopPadding` و`BottomPadding` ملكيات.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## الخطوة 7: أضف محتوى إلى الصف
الآن نستطيع

 سنقوم بإضافة محتوى إلى السطر باستخدام طرق مُنشئ المستند. في هذا المثال ، نستخدم الامتداد`Writeln()` طريقة لإضافة نص إلى السطر.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## الخطوة 8: قم بإنهاء السطر والجدول
 بمجرد إضافة المحتوى إلى الصف ، يمكننا إنهاء الصف باستخدام`EndRow()` الطريقة ثم قم بإنهاء الجدول باستخدام`EndTable()` طريقة.

```csharp
builder. EndRow();
builder. EndTable();
```

## الخطوة 9: احفظ المستند المعدل
أخيرًا ، نحفظ المستند المعدل في ملف. يمكنك اختيار اسم وموقع مناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

تهنئة ! لقد قمت الآن بتطبيق تنسيق الصف على جدول باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لتطبيق تنسيق الصف باستخدام Aspose.Words for .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تطبيق تنسيق الصفوف على جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة دمج هذه الوظيفة في مشاريع C # الخاصة بك. تعد معالجة تنسيق صفوف الجدول جانبًا أساسيًا من جوانب معالجة المستندات ، وتوفر Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لتحقيق ذلك. باستخدام هذه المعرفة ، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية المتطلبات المحددة.