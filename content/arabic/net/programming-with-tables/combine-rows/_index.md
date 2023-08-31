---
title: الجمع بين الصفوف
linktitle: الجمع بين الصفوف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية دمج صفوف الجدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/combine-rows/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Words for .NET لدمج صفوف الجداول في مستند Word. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من معالجة صفوف الجدول ودمجها في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجداول
لبدء معالجة الكلمات بالجداول، نحتاج إلى تحميل المستند الذي يحتوي عليها والوصول إليها. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");

// الوصول إلى الجداول
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: دمج صفوف الجدول
بعد ذلك، سنقوم بدمج صفوف الجدول الثاني إلى نهاية الجدول الأول. استخدم الكود التالي:

```csharp
// مزيج من صفوف الجدول
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 هنا نستخدم أ`while` حلقة للتكرار على كافة صفوف المصفوفة الثانية وإضافتها إلى نهاية المصفوفة الأولى باستخدام`Add` طريقة. بعد ذلك، نقوم بإزالة الجدول الثاني من المستند باستخدام الأمر`Remove` طريقة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل مع صفوف الجدول المدمجة. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لدمج الصفوف باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// سيتم إلحاق الصفوف من الجدول الثاني بنهاية الجدول الأول.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// إلحاق كافة الصفوف من الجدول الحالي بالجداول التالية
	// مع عدد خلايا مختلفة وعرضها يمكن ضمها إلى جدول واحد.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية دمج صفوف الجداول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك التعامل مع صفوف الجدول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة دمج بياناتك وتنظيمها بكفاءة في جدول.