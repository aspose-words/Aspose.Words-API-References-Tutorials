---
title: تطبيق حدود المخطط التفصيلي
linktitle: تطبيق حدود المخطط التفصيلي
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتطبيق حدود المخطط على جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتطبيق حد مخطط على جدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، سيكون لديك فهم واضح لكيفية التعامل مع حدود الجدول في مستندات Word باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يتم فيه تخزين مستند Word الخاص بك. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
 بعد ذلك ، تحتاج إلى تحميل مستند Word في مثيل لـ`Document` فصل.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: الوصول إلى الجدول
 لتطبيق حدود المخطط ، نحتاج إلى الوصول إلى الجدول في المستند. ال`Table` يمثل class جدولًا في Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## الخطوة 4: قم بمحاذاة الجدول إلى وسط الصفحة
 الآن يمكننا محاذاة الجدول إلى وسط الصفحة باستخدام`Alignment` خاصية الجدول.

```csharp
table. Alignment = Table Alignment. Center;
```

## الخطوة 5: محو حدود الجدول الموجودة
للبدء بحدود خارجية جديدة ، نحتاج أولاً إلى محو كل الحدود الموجودة من الجدول. يمكن القيام بذلك باستخدام ملف`ClearBorders()` طريقة.

```csharp
table. ClearBorders();
```

## الخطوة 6: تحديد حد أخضر حول الجدول
 يمكننا الآن تعيين حد أخضر حول الجدول باستخدام`SetBorder()` طريقة لكل جانب من الجدول. في هذا المثال ، نستخدم حدًا من النوع "مفرد" بسمك 1.5 نقطة ولون أخضر.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## الخطوة 7: املأ الخلايا بلون الخلفية
لتحسين العرض المرئي للجدول ، يمكننا ملء الخلايا بلون خلفية الأرض

فكرة. في هذا المثال ، نستخدم اللون الأخضر الفاتح.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## الخطوة 8: احفظ المستند المعدل
أخيرًا ، نحفظ المستند المعدل في ملف. يمكنك اختيار اسم وموقع مناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

تهنئة ! لقد قمت الآن بتطبيق حد مخطط على جدول باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لـ Apply Outline Border باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// قم بمحاذاة الجدول إلى وسط الصفحة.
	table.Alignment = TableAlignment.Center;
	//امسح أي حدود موجودة من الجدول.
	table.ClearBorders();
	// ضع حدًا أخضر حول الطاولة وليس بالداخل.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// املأ الخلايا بلون أخضر فاتح.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تطبيق حد مخطط على جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة دمج هذه الوظيفة في مشاريع C # الخاصة بك. يعد التلاعب بتنسيق الجدول جانبًا أساسيًا من معالجة المستندات ، ويقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لتحقيق ذلك. باستخدام هذه المعرفة ، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية المتطلبات المحددة.