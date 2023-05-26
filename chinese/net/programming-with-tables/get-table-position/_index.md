---
title: الحصول على الجدول الموقف
linktitle: الحصول على الجدول الموقف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الحصول على موضع الجدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-tables/get-table-position/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية الحصول على موضع الجدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من الحصول على خصائص تحديد موضع الجدول في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء العمل مع الجدول ، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");

// الوصول إلى المصفوفة
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات. تأكد أيضًا من احتواء المستند على الجدول الذي تريد الحصول على موضعه.

## الخطوة 3: الحصول على خصائص وضع الصفيف
بعد ذلك ، سوف نتحقق من نوع تحديد الموضع للمصفوفة ونحصل على خصائص تحديد الموضع المناسبة. استخدم الكود التالي:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 هنا نستخدم شرطًا للتحقق مما إذا كانت المصفوفة من النوع العائم. إذا كان الأمر كذلك ، فنحن نطبع ملف`RelativeHorizontalAlignment` و`RelativeVerticalAlignment` للحصول على المحاذاة النسبية الأفقية والعمودية للجدول. خلاف ذلك ، نقوم بطباعة ملف`Alignment` الخاصية للحصول على محاذاة الصفيف.

### عينة من التعليمات البرمجية المصدر لـ Get Table Position باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على موضع الجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك الحصول على خصائص موضع الجدول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تحليل المصفوفات ومعالجتها وفقًا لمواضعها المحددة.