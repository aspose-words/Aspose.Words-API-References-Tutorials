---
title: تطبيق تنسيق الصف
linktitle: تطبيق تنسيق الصف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتطبيق تنسيق الصف على جدول باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتطبيق تنسيق الصف على جدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح لكيفية تنسيق صفوف الجدول في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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

## الخطوة 3: بدء مجلس جديد
 لتطبيق تنسيق الصف، يجب علينا أولاً أن نبدأ جدولاً جديدًا باستخدام الأمر`StartTable()` طريقة منشئ الوثيقة.

```csharp
Table table = builder. StartTable();
```

## الخطوة 4: أدخل الخلية وانتقل إلى تنسيق الصف
يمكننا الآن إدراج خلية في الجدول والوصول إلى تنسيق الصف لتلك الخلية باستخدام أداة إنشاء المستندات`InsertCell()` و`RowFormat` طُرق.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## الخطوة 5: ضبط ارتفاع الصف
 لتعيين ارتفاع الصف، نستخدم`Height` و`HeightRule` خصائص تنسيق الصف. في هذا المثال، قمنا بتعيين ارتفاع الصف بمقدار 100 نقطة واستخدمنا`Exactly` قاعدة.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## الخطوة 6: تحديد تنسيق الجدول
 يمكن تعيين بعض خصائص التنسيق على الجدول نفسه وتطبيقها على كافة صفوف الجدول. في هذا المثال، قمنا بتعيين خصائص هامش الجدول باستخدام`LeftPadding`, `RightPadding`, `TopPadding` و`BottomPadding` ملكيات.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## الخطوة 7: إضافة محتوى إلى الصف
الآن نستطيع

 سنقوم بإضافة محتوى إلى السطر باستخدام أساليب منشئ المستند. في هذا المثال نستخدم`Writeln()` طريقة إضافة نص إلى السطر.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## الخطوة 8: إنهاء السطر والجدول
 بمجرد إضافة المحتوى إلى الصف، يمكننا إنهاء الصف باستخدام`EndRow()` الطريقة ثم قم بإنهاء الجدول باستخدام`EndTable()` طريقة.

```csharp
builder. EndRow();
builder. EndTable();
```

## الخطوة 9: احفظ المستند المعدل
وأخيرًا، نقوم بحفظ المستند المعدل في ملف. يمكنك اختيار الاسم والموقع المناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

تهنئة ! لقد قمت الآن بتطبيق تنسيق الصف على جدول باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لتطبيق تنسيق الصف باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تطبيق تنسيق الصف على جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي، يمكنك بسهولة دمج هذه الوظيفة في مشاريع C# الخاصة بك. تعد معالجة تنسيق صف الجدول جانبًا أساسيًا من معالجة المستندات، ويوفر Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لتحقيق ذلك. باستخدام هذه المعرفة، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية متطلبات محددة.