---
title: انقسام الجدول
linktitle: انقسام الجدول
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/split-table/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من تقسيم جدول من صف معين في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند
لبدء العمل مع المستند ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى دليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: قسمة الجدول
بعد ذلك سنقوم بتقسيم الجدول من صف معين. استخدم الكود التالي:

```csharp
// استرجع الجدول الأول
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// تحديد الخط الذي سيتم تقسيم الجدول منه
Row row = firstTable.Rows[2];

// قم بإنشاء حاوية جديدة للجدول المقسم
Table table = (Table)firstTable.Clone(false);

// أدخل الحاوية بعد الجدول الأصلي
firstTable.ParentNode.InsertAfter(table, firstTable);

// أضف فقرة عازلة للحفاظ على مسافة بين الجداول
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// انقل الصفوف من الجدول الأصلي إلى جدول الانقسام
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

هنا نستخدم المستند لاسترداد الجدول الأول من عقدة المستند. ثم نحدد الصف الذي نريد تقسيم الجدول منه ، في هذا المثال هو الصف الثالث (الفهرس 2). نقوم بعد ذلك بإنشاء حاوية جديدة عن طريق استنساخ الجدول الأصلي ثم إدخاله بعد الجدول الأصلي. نضيف أيضًا فقرة عازلة للحفاظ على مسافة بين الجدولين. ثم ننقل الصفوف من الجدول الأصلي إلى الجدول المنفصل باستخدام حلقة do-while حتى نصل إلى الصف المحدد.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ ملف

  تم تعديل المستند باستخدام الجدول المقسم. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Split Table باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// سنقوم بتقسيم الجدول في الصف الثالث (ضمناً).
Row row = firstTable.Rows[2];
// قم بإنشاء حاوية جديدة للجدول المقسم.
Table table = (Table) firstTable.Clone(false);
// أدخل الحاوية بعد الأصل.
firstTable.ParentNode.InsertAfter(table, firstTable);
// أضف فقرة عازلة لضمان بقاء الجداول منفصلة.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك بسهولة تقسيم الجداول من سطر معين في مستندات Word الخاصة بك.