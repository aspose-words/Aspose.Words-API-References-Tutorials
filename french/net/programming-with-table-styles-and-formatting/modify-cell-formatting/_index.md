---
title: تعديل تنسيق الخلية
linktitle: تعديل تنسيق الخلية
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتغيير تنسيق خلية في جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/modify-cell-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتغيير تنسيق الخلية باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تغيير العرض والاتجاه ولون الخلفية لخلية في جدول في مستندات Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: انتقل إلى الخلية للتعديل
 لتغيير تنسيق الخلية ، نحتاج إلى الانتقال إلى الخلية المحددة في الجدول. نحن نستخدم ال`GetChild()` و`FirstRow.FirstCell` طرق للحصول على المرجع إلى الخلية الأولى من المصفوفة الأولى.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## الخطوة 4: تغيير تنسيق الخلية
 الآن يمكننا تغيير تنسيق الخلية باستخدام خصائص ملف`CellFormat` فصل. على سبيل المثال ، يمكننا ضبط عرض الخلية واتجاه النص ولون الخلفية.

```csharp
firstCell.CellFormat.Width = 30;
firstCell.CellFormat.Orientation = TextOrientation.Downward;
firstCell.CellFormat.Shading.ForegroundPatternColor = Color.LightGreen;
```

### نموذج التعليمات البرمجية المصدر لتعديل تنسيق الخلية باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	firstCell.CellFormat.Width = 30;
	firstCell.CellFormat.Orientation = TextOrientation.Downward;
	firstCell.CellFormat.Shading.ForegroundPatternColor = Color.LightGreen;
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تغيير تنسيق خلية في جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة ضبط عرض الخلية والاتجاه ولون الخلفية في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك الخاصة.