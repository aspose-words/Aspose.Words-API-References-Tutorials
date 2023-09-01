---
title: تعديل تنسيق الصف
linktitle: تعديل تنسيق الصف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتغيير تنسيق صف الجدول باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتغيير تنسيق صف الجدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية تغيير الحدود والارتفاع وفاصل الأسطر لصف جدول في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

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

## الخطوة 3: الوصول إلى الخط للتعديل
 لتغيير تنسيق صف الجدول، نحتاج إلى الانتقال إلى الصف المحدد في الجدول. نحن نستخدم ال`GetChild()` و`FirstRow` طرق للحصول على المرجع إلى الصف الأول من الجدول.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## الخطوة 4: تغيير تنسيق الصف
 يمكننا الآن تغيير تنسيق الصف باستخدام خصائص الملف`RowFormat` فصل. على سبيل المثال، يمكننا إزالة حدود الأسطر وضبط الارتفاع التلقائي والسماح بفاصل الأسطر.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### نموذج التعليمات البرمجية المصدر لتعديل تنسيق الصف باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// استرداد الصف الأول في الجدول.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تغيير تنسيق صف الجدول باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي، يمكنك بسهولة ضبط الحدود والارتفاع وفاصل الأسطر للصفوف في الجداول في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تخصيص التخطيط المرئي لجداولك وفقًا لاحتياجاتك المحددة.