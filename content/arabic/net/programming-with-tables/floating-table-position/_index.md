---
title: موضع الجدول العائم
linktitle: موضع الجدول العائم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية وضع جدول في موضع عائم في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/floating-table-position/
---

في هذا البرنامج التعليمي، سنتعلم كيفية استخدام Aspose.Words لـ .NET لوضع جدول في موضع عائم في مستند Word. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستكون قادرًا على التحكم في موضع الجداول العائمة ومحاذاتها في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء معالجة الكلمات بالجدول، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// الوصول إلى المصفوفة
Table table = doc.FirstSection.Body.Tables[0];
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك. تأكد أيضًا من أن المستند يحتوي على جدول سيتم وضعه في موضع عائم.

## الخطوة 3: تحديد موضع اللوحة العائمة
بعد ذلك، سنقوم بوضع الجدول في موضع عائم باستخدام الخصائص التي يوفرها Aspose.Words لـ .NET. استخدم الكود التالي:

```csharp
// تحديد موضع الجدول العائم
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 هنا نستخدم`AbsoluteHorizontalDistance` خاصية لتعيين المسافة الأفقية المطلقة للجدول من الحافة اليسرى للصفحة. نحن نستخدم أيضًا`RelativeVerticalAlignment` الخاصية لتعيين المحاذاة الرأسية النسبية للجدول مع المحتوى المحيط.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل مع وضع الجدول في موضع عائم. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لموضع الجدول العائم باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية وضع جدول في موضع عائم في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك التحكم في موضع الجداول العائمة ومحاذاتها في مستندات Word الخاصة بك برمجيًا.