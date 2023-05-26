---
title: حافظ على الجدول معًا
linktitle: حافظ على الجدول معًا
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/keep-table-together/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من الحفاظ على الجدول سليمًا دون تقسيمه عبر صفحات متعددة في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند واسترجاع الجدول
لبدء العمل مع الجدول ، نحتاج إلى تحميل المستند وإحضار الجدول الذي نريد الاحتفاظ به معًا. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// استرجع الجدول
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: تفعيل خيار "KeepWithNext"
للحفاظ على الجدول معًا ومنع انقسامه عبر صفحات متعددة ، نحتاج إلى تمكين الخيار "KeepWithNext" لكل فقرة في الجدول باستثناء الفقرات الأخيرة من الصف الأخير من الجدول. استخدم الكود التالي:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

هنا نقوم بعمل حلقة عبر كل خلية في الجدول وتمكين خيار "KeepWithNext" لكل فقرة في الخلية باستثناء الفقرات الأخيرة من الصف الأخير في الجدول.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع تثبيت الجدول معًا. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر لـ Keep Table Together باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// نحتاج إلى تمكين KeepWithNext لكل فقرة في الجدول لمنعها من اختراق الصفحة ،
	// باستثناء الفقرات الأخيرة في الصف الأخير من الجدول.
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
في هذا البرنامج التعليمي ، تعلمنا كيفية تجميع الجدول معًا في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك الحفاظ على الجدول سليمًا ومنعه من الانقسام عبر صفحات متعددة في مستنداتك. تمنحك هذه الميزة مزيدًا من التحكم في مظهر الجداول وتخطيطها في مستنداتك.