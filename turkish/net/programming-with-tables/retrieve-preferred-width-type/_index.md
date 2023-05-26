---
title: استرجاع نوع العرض المفضل
linktitle: استرجاع نوع العرض المفضل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استرداد النوع وقيمة العرض المفضلة لخلية في جدول Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/retrieve-preferred-width-type/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استرداد نوع العرض المفضل وقيمته من خلية جدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من استرداد نوع العرض المفضل (مطلق أو نسبي أو تلقائي) وقيمته لخلية معينة في جداول مستندات Word الخاصة بك.

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

## الخطوة 3: استرجاع نوع العرض وقيمته المفضلين
بعد ذلك ، سنقوم باسترداد نوع العرض المفضل وقيمته لخلية جدول معينة. استخدم الكود التالي:

```csharp
// استرجع الجدول
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// تنشيط الضبط التلقائي للجدول
table. AllowAutoFit = true;

// استرجع الخلية الأولى من الصف الأول
Cell firstCell = table.FirstRow.FirstCell;

// استرجع نوع العرض المفضل وقيمته
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

هنا نستخدم المستند لجلب الجدول الأول ، ثم نقوم بتمكين الجدول التلقائي الملائم مع`AllowAutoFit` ملكية. ثم نسترجع الخلية الأولى من الصف الأول من الجدول. من هذه الخلية ، يمكننا استرداد نوع العرض المفضل بامتداد`PreferredWidth.Type` الممتلكات وقيمتها مع`PreferredWidth.Value` ملكية.

### نموذج التعليمات البرمجية المصدر لـ Retrieve Preferred Width Type باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية استرداد نوع العرض المفضل وقيمته من خلية جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك استرداد هذه المعلومات لخلايا معينة في جداول مستندات Word الخاصة بك.