---
title: ضم الصفوف
linktitle: ضم الصفوف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية دمج صفوف الجدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-tables/combine-rows/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words for .NET لدمج صفوف الجداول في مستند Word. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من معالجة ودمج صفوف الجدول في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند والوصول إلى الجداول
لبدء العمل مع الجداول ، نحتاج إلى تحميل المستند الذي يحتوي عليها والوصول إليها. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");

// الوصول إلى الجداول
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: دمج صفوف الجدول
بعد ذلك ، سنجمع صفوف الجدول الثاني في نهاية الجدول الأول. استخدم الكود التالي:

```csharp
// مزيج من صفوف الجدول
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 هنا نستخدم ملف`while` loop للتكرار على جميع صفوف المصفوفة الثانية وإضافتها إلى نهاية المصفوفة الأولى باستخدام`Add` طريقة. بعد ذلك ، نقوم بإزالة الجدول الثاني من المستند باستخدام ملف`Remove` طريقة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع صفوف الجدول المدمجة. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر لـ Combine Rows باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// سيتم إلحاق الصفوف من الجدول الثاني بنهاية الجدول الأول.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// إلحاق كافة الصفوف من الجدول الحالي بالجداول التالية
	// مع عدد الخلايا المختلفة والعروض يمكن ضمها في جدول واحد.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية دمج صفوف الجداول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك معالجة صفوف الجدول في مستندات Word برمجيًا. تتيح لك هذه الميزة دمج البيانات وتنظيمها في جدول بكفاءة.