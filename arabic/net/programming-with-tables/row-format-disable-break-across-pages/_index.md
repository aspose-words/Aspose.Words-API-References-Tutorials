---
title: تنسيق الصف تعطيل الفاصل عبر الصفحات
linktitle: تنسيق الصف تعطيل الفاصل عبر الصفحات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعطيل فاصل الأسطر لجدول عبر صفحات متعددة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/row-format-disable-break-across-pages/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تعطيل فاصل الأسطر لجدول متعدد الصفحات في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تعطيل فصل الأسطر لجميع الصفوف في الجدول الخاص بك في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند
لبدء معالجة الكلمات بالمستند ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى دليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: تعطيل فاصل صفوف الجدول
بعد ذلك ، سنقوم بتعطيل فصل الصفوف لجميع الصفوف في الجدول. استخدم الكود التالي:

```csharp
// استرجع الجدول
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// تعطيل فاصل الصف لجميع الصفوف في الجدول
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 هنا نستخدم المستند لجلب الجدول الأول ثم نكرره عبر جميع الصفوف في الجدول باستخدام حلقة foreach. داخل الحلقة ، نقوم بتعطيل فصل الصفوف لكل صف عن طريق ضبط`RowFormat.AllowBreakAcrossPages` ملكية ل`false`.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع تعطيل فاصل أسطر الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لتنسيق الصف تعطيل الفاصل عبر الصفحات باستخدام Aspose.Words for .NET 

```csharp
//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// تعطيل التقسيم عبر الصفحات لجميع الصفوف في الجدول.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعطيل فاصل الأسطر لجدول متعدد الصفحات في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تطبيق هذا التعطيل على جداولك في مستندات Word الخاصة بك.