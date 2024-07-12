---
title: حافظ على الطاولة معًا
linktitle: حافظ على الطاولة معًا
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/keep-table-together/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على الحفاظ على جدول سليم دون تقسيمه عبر صفحات متعددة في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند واسترجاع الجدول
لبدء معالجة الكلمات بالجدول، نحتاج إلى تحميل المستند وإحضار الجدول الذي نريد الاحتفاظ به معًا. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// استرداد الجدول
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: تمكين خيار "KeepWithNext".
للحفاظ على الجدول معًا ومنعه من الانقسام عبر صفحات متعددة، نحتاج إلى تمكين خيار "KeepWithNext" لكل فقرة في الجدول باستثناء الفقرات الأخيرة من الصف الأخير من الجدول. استخدم الكود التالي:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

نحن هنا نتنقل عبر كل خلية في الجدول ونقوم بتمكين خيار "KeepWithNext" لكل فقرة في الخلية باستثناء الفقرات الأخيرة من الصف الأخير في الجدول.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل مع إبقاء الجدول معًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لبرنامج Keep Table Together باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// نحن بحاجة إلى تمكين KeepWithNext لكل فقرة في الجدول لمنعها من الانقسام عبر الصفحة.
	//باستثناء الفقرات الأخيرة في الصف الأخير من الجدول.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك الحفاظ على جدول سليم ومنعه من الانقسام عبر صفحات متعددة في مستنداتك. تمنحك هذه الميزة مزيدًا من التحكم في مظهر وتخطيط الجداول في مستنداتك.