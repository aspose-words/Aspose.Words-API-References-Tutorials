---
title: تنسيق الصف تعطيل الفاصل عبر الصفحات
linktitle: تنسيق الصف تعطيل الفاصل عبر الصفحات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعطيل فاصل الأسطر لجدول عبر صفحات متعددة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/row-format-disable-break-across-pages/
---

في هذا البرنامج التعليمي، سنتعلم كيفية تعطيل فاصل الأسطر لجدول متعدد الصفحات في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستتمكن من تعطيل فصل الأسطر لجميع الصفوف في الجدول الخاص بك في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل الوثيقة
لبدء معالجة الكلمات مع المستند، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: تعطيل فاصل صفوف الجدول
بعد ذلك، سنقوم بتعطيل كسر الصفوف لجميع الصفوف في الجدول. استخدم الكود التالي:

```csharp
// استرداد الجدول
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// تعطيل فاصل الصفوف لجميع الصفوف في الجدول
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 هنا نستخدم المستند لجلب الجدول الأول ثم نمر عبر جميع الصفوف في الجدول باستخدام حلقة foreach. داخل الحلقة، نقوم بتعطيل كسر الصفوف لكل صف عن طريق تعيين`RowFormat.AllowBreakAcrossPages` الملكية ل`false`.

## الخطوة 4: حفظ المستند المعدل
وأخيرًا، نحتاج إلى حفظ المستند المعدل مع تعطيل فاصل أسطر الجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لتنسيق الصف تعطيل الفاصل عبر الصفحات باستخدام Aspose.Words لـ .NET 

```csharp
//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// تعطيل التقسيم عبر الصفحات لجميع الصفوف في الجدول.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعطيل فاصل الأسطر لجدول متعدد الصفحات في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك تطبيق هذا التعطيل على جداولك في مستندات Word الخاصة بك.