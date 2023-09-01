---
title: جدول الانقسام
linktitle: جدول الانقسام
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/split-table/
---

في هذا البرنامج التعليمي، سنتعلم كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من تقسيم جدول من صف معين في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل الوثيقة
لبدء معالجة الكلمات مع المستند، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: تقسيم الجدول
بعد ذلك سنقوم بتقسيم الجدول من صف معين. استخدم الكود التالي:

```csharp
// استرداد الجدول الأول
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// تحديد الخط الذي سيتم تقسيم الجدول منه
Row row = firstTable.Rows[2];

// قم بإنشاء حاوية جديدة للجدول المقسم
Table table = (Table)firstTable.Clone(false);

// أدخل الحاوية بعد الجدول الأصلي
firstTable.ParentNode.InsertAfter(table, firstTable);

// أضف فقرة عازلة للحفاظ على المسافة بين الجداول
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// نقل الصفوف من الجدول الأصلي إلى الجدول المقسم
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

هنا نستخدم المستند لاسترداد الجدول الأول من عقدة المستند. ثم نحدد الصف الذي نريد تقسيم الجدول منه، في هذا المثال هو الصف الثالث (الفهرس 2). نقوم بعد ذلك بإنشاء حاوية جديدة عن طريق استنساخ الجدول الأصلي ثم إدراجها بعد الجدول الأصلي. نضيف أيضًا فقرة عازلة للحفاظ على المسافة بين الجدولين. ثم نقوم بنقل الصفوف من الجدول الأصلي إلى الجدول المقسم باستخدام حلقة do-while حتى نصل إلى الصف المحدد.

## الخطوة 4: حفظ المستند المعدل
وأخيرا، نحن بحاجة إلى حفظ

  تم تعديل الوثيقة باستخدام الجدول المقسم. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Split Table باستخدام Aspose.Words لـ .NET 

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// سنقوم بتقسيم الجدول في الصف الثالث (ضمنا).
Row row = firstTable.Rows[2];
// قم بإنشاء حاوية جديدة للجدول المقسم.
Table table = (Table) firstTable.Clone(false);
// أدخل الحاوية بعد الأصل.
firstTable.ParentNode.InsertAfter(table, firstTable);
// أضف فقرة عازلة لضمان بقاء الجداول متباعدة.
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
في هذا البرنامج التعليمي، تعلمنا كيفية تقسيم جدول في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك بسهولة تقسيم الجداول من سطر معين في مستندات Word الخاصة بك.