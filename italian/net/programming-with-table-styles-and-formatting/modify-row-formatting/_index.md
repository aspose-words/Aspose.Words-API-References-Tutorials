---
title: تعديل تنسيق الصف
linktitle: تعديل تنسيق الصف
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتغيير تنسيق صف الجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتغيير تنسيق صف الجدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تغيير الحدود والارتفاع وفاصل الأسطر لصف جدول في مستندات Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: الوصول إلى الخط لتعديله
 لتغيير تنسيق صف الجدول ، نحتاج إلى الانتقال إلى الصف المحدد في الجدول. نحن نستخدم ال`GetChild()` و`FirstRow` طرق للحصول على المرجع للصف الأول من الجدول.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## الخطوة 4: تغيير تنسيق الصف
 الآن يمكننا تغيير تنسيق الصف باستخدام خصائص ملف`RowFormat` فصل. على سبيل المثال ، يمكننا إزالة حدود الخط وتعيين الارتفاع التلقائي والسماح بفاصل الأسطر.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### نموذج التعليمات البرمجية المصدر لتعديل تنسيق الصف باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// استرجع الصف الأول في الجدول.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تغيير تنسيق صف الجدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة ضبط الحدود والارتفاع وفاصل الأسطر للصفوف في الجداول الخاصة بك في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك الخاصة.