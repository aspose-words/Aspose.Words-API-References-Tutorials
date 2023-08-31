---
title: اضبط الموضع الأفقي أو الرأسي النسبي
linktitle: اضبط الموضع الأفقي أو الرأسي النسبي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين الموضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

في هذا البرنامج التعليمي، سنتعلم كيفية تعيين الموضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على ضبط الموضع الأفقي أو الرأسي النسبي لجدولك في مستندات Word.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل الوثيقة
لبدء معالجة الكلمات مع المستند، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك وقم بتوفير اسم الملف الصحيح.

## الخطوة 3: تحديد الموضع النسبي للجدول
بعد ذلك، سنقوم بتعيين الموضع الأفقي أو الرأسي النسبي للجدول. استخدم الكود التالي:

```csharp
// استرداد الجدول
Table table = doc.FirstSection.Body.Tables[0];

//تعريف الوضع الأفقي النسبي للجدول
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// تحديد الموضع الرأسي النسبي للجدول
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 هنا نستخدم الوثيقة لاسترداد الجدول الأول من نص القسم الأول. بعد ذلك، قمنا بتعيين الموضع الأفقي النسبي للجدول باستخدام`HorizontalAnchor` الملكية باستخدام`RelativeHorizontalPosition.Column` قيمة. وبالمثل، قمنا بتعيين الموضع الرأسي النسبي للجدول باستخدام`VerticalAnchor` الملكية باستخدام`RelativeVerticalPosition.Page` قيمة.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل مع تحديد الموضع النسبي للجدول. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لتعيين الموضع الأفقي أو الرأسي النسبي باستخدام Aspose.Words لـ .NET 

```csharp
//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين الموضع الأفقي أو الرأسي النسبي للجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك تطبيق هذا الموضع النسبي على جداولك في مستندات Word الخاصة بك.