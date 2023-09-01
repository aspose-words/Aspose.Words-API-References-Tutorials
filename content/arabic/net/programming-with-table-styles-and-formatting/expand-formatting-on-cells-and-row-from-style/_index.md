---
title: قم بتوسيع التنسيق على الخلايا والصف من النمط
linktitle: قم بتوسيع التنسيق على الخلايا والصف من النمط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتوسيع التنسيق إلى الخلايا والصفوف من نمط جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتوسيع التنسيق إلى الخلايا والصفوف من نمط باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية تطبيق تنسيق نمط الجدول على خلايا وصفوف معينة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.


## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الخاص بك. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند الموجود
 بعد ذلك، تحتاج إلى تحميل مستند Word الموجود في مثيل`Document` فصل.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: انتقل إلى الخلية الأولى من الجدول الأول
 للبدء، نحتاج إلى الانتقال إلى الخلية الأولى في الجدول الأول في المستند. نحن نستخدم ال`GetChild()` و`FirstRow.FirstCell` طرق الحصول على المرجع إلى الخلية الأولى.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## الخطوة 4: إظهار تنسيق الخلية الأولي
قبل توسيع أنماط الجدول، نعرض لون الخلفية الحالي للخلية. يجب أن يكون هذا فارغًا لأن التنسيق الحالي مخزن في نمط الجدول.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## الخطوة 5: قم بتوسيع أنماط الجدول إلى التنسيق المباشر
 نقوم الآن بتوسيع أنماط الجدول إلى التنسيق المباشر باستخدام المستند`ExpandTableStylesToDirectFormatting()` طريقة.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## الخطوة 6: إظهار تنسيق الخلية بعد توسيع النمط
نقوم الآن بعرض لون خلفية الخلية بعد توسيع أنماط الجدول. يجب تطبيق لون خلفية أزرق من نمط الجدول.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### نموذج التعليمات البرمجية المصدر لتوسيع التنسيق على الخلايا والصف من النمط باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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
	// يجب أن يتم تطبيق لون نمط الخلفية الزرقاء من نمط الجدول.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية توسيع التنسيق ليشمل الخلايا والصفوف من نمط جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة، يمكنك بسهولة تطبيق تنسيق نمط الجدول على خلايا وصفوف معينة في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تخصيص تخطيط وعرض مستندات Word الخاصة بك بشكل أكبر.