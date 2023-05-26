---
title: موقف الجدول العائم
linktitle: موقف الجدول العائم
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية وضع جدول في موضع متحرك في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/floating-table-position/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لوضع جدول في موضع عائم في مستند Word. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من التحكم في موضع ومحاذاة الجداول العائمة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء العمل مع الجدول ، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// الوصول إلى المصفوفة
Table table = doc.FirstSection.Body.Tables[0];
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات. تأكد أيضًا من احتواء المستند على جدول سيتم وضعه في موضع عائم.

## الخطوة 3: وضع اللوح العائم
بعد ذلك ، سنضع الجدول في موضع عائم باستخدام الخصائص التي توفرها Aspose.Words for .NET. استخدم الكود التالي:

```csharp
// وضع الجدول العائم
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 هنا نستخدم ملف`AbsoluteHorizontalDistance` خاصية لتعيين المسافة الأفقية المطلقة للجدول من الحافة اليسرى للصفحة. نستخدم أيضًا ملف`RelativeVerticalAlignment` لتعيين المحاذاة الرأسية النسبية للجدول للمحتوى المحيط.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع وضع الجدول في موضع عائم. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Floating Table Position باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية وضع جدول في موضع عائم في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك التحكم في موضع ومحاذاة الجداول العائمة في مستندات Word الخاصة بك برمجيًا.