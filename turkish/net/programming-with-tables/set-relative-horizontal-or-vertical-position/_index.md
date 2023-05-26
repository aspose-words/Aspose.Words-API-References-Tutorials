---
title: تعيين الوضع الأفقي أو الرأسي النسبي
linktitle: تعيين الوضع الأفقي أو الرأسي النسبي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين الوضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تعيين الوضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستكون قادرًا على تعيين الوضع الأفقي أو الرأسي النسبي لجدولك في مستندات Word الخاصة بك.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند
لبدء العمل مع المستند ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى دليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: تحديد الموضع النسبي للجدول
بعد ذلك ، سنقوم بتعيين الوضع النسبي الأفقي أو الرأسي للجدول. استخدم الكود التالي:

```csharp
// استرجع الجدول
Table table = doc.FirstSection.Body.Tables[0];

//تعريف الوضع الأفقي النسبي للجدول
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// تحديد الوضع الرأسي النسبي للجدول
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 هنا نستخدم المستند لاسترداد الجدول الأول من نص القسم الأول. بعد ذلك ، قمنا بتعيين الموضع الأفقي النسبي للجدول بامتداد`HorizontalAnchor` الملكية باستخدام`RelativeHorizontalPosition.Column` قيمة. وبالمثل ، قمنا بتعيين الوضع الرأسي النسبي للجدول بامتداد`VerticalAnchor` الملكية باستخدام`RelativeVerticalPosition.Page` قيمة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع تحديد الموضع النسبي للجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر لـ Set Relative Horizontal Or Vertical Position باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين الوضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تطبيق هذا الموضع النسبي على جداولك في مستندات Word الخاصة بك.