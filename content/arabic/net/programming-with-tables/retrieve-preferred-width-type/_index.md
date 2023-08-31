---
title: استرداد نوع العرض المفضل
linktitle: استرداد نوع العرض المفضل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد النوع وقيمة العرض المفضل للخلية في جدول Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/retrieve-preferred-width-type/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استرداد نوع العرض المفضل وقيمته من خلية جدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من استرداد نوع العرض المفضل (مطلق أو نسبي أو تلقائي) وقيمته لخلية معينة في جداول مستندات Word.

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

## الخطوة 3: استرداد نوع العرض المفضل وقيمته
بعد ذلك، سنقوم باسترداد نوع العرض المفضل وقيمته لخلية جدول معينة. استخدم الكود التالي:

```csharp
// استرداد الجدول
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// تفعيل التعديل التلقائي للجدول
table. AllowAutoFit = true;

// استرداد الخلية الأولى من الصف الأول
Cell firstCell = table.FirstRow.FirstCell;

// استرجع نوع العرض المفضل وقيمته
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

هنا نستخدم المستند لجلب الجدول الأول، ثم نقوم بتمكين الجدول التلقائي الذي يتناسب مع`AllowAutoFit` ملكية. ثم نقوم باسترداد الخلية الأولى من الصف الأول من الجدول. من هذه الخلية، يمكننا استرداد نوع العرض المفضل باستخدام الملف`PreferredWidth.Type` الملكية وقيمتها مع`PreferredWidth.Value` ملكية.

### نموذج التعليمات البرمجية المصدر لاسترداد نوع العرض المفضل باستخدام Aspose.Words لـ .NET 

```csharp
//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استرداد نوع العرض المفضل وقيمته من خلية جدول في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك استرداد هذه المعلومات لخلايا محددة في جداول مستندات Word.