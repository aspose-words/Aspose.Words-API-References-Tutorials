---
title: قم بتوسيع التنسيق في الخلايا والصف من النمط
linktitle: قم بتوسيع التنسيق في الخلايا والصف من النمط
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتوسيع التنسيق إلى الخلايا والصفوف من نمط الجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتوسيع التنسيق إلى الخلايا والصفوف من نمط باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تطبيق تنسيق نمط الجدول على خلايا وصفوف معينة في مستندات Word باستخدام Aspose.Words for .NET.


## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الخاص بك. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند الحالي
 بعد ذلك ، تحتاج إلى تحميل مستند Word الموجود في مثيل`Document` فصل.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: اذهب إلى الخلية الأولى من الجدول الأول
 للبدء ، نحتاج إلى الانتقال إلى الخلية الأولى من الجدول الأول في المستند. نحن نستخدم ال`GetChild()` و`FirstRow.FirstCell` طرق للحصول على المرجع للخلية الأولى.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## الخطوة 4: إظهار التنسيق الأولي للخلايا
قبل توسيع أنماط الجدول ، نعرض لون الخلفية الحالي للخلية. يجب أن يكون هذا فارغًا لأن التنسيق الحالي مخزن في نمط الجدول.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## الخطوة 5: قم بتوسيع أنماط الجدول إلى التنسيق المباشر
 نقوم الآن بتوسيع أنماط الجدول لتوجيه التنسيق باستخدام المستند`ExpandTableStylesToDirectFormatting()` طريقة.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## الخطوة 6: إظهار تنسيق الخلية بعد توسيع النمط
نعرض الآن لون خلفية الخلية بعد توسيع أنماط الجدول. يجب تطبيق لون خلفية أزرق من نمط الجدول.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### عينة من التعليمات البرمجية المصدر لتوسيع التنسيق على الخلايا والصف من النمط باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// احصل على الخلية الأولى من الجدول الأول في المستند.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// قم أولاً بطباعة لون تظليل الخلية.
	// يجب أن يكون هذا فارغًا حيث يتم تخزين التظليل الحالي في نمط الجدول.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// الآن قم بطباعة تظليل الخلية بعد توسيع أنماط الجدول.
	// يجب تطبيق لون نقش خلفية أزرق من نمط الجدول.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية توسيع التنسيق إلى الخلايا والصفوف من نمط الجدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تطبيق تنسيق نمط الجدول على خلايا وصفوف معينة في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص التخطيط والعرض التقديمي لمستندات Word الخاصة بك.