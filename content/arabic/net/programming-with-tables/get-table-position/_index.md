---
title: الحصول على موقف الجدول
linktitle: الحصول على موقف الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد موضع الجدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/get-table-position/
---

في هذا البرنامج التعليمي، سنتعلم كيفية تحديد موضع الجدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من الحصول على خصائص تحديد موضع الجدول في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء معالجة الكلمات بالجدول، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Tables.docx");

// الوصول إلى المصفوفة
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك. تأكد أيضًا من أن المستند يحتوي على الجدول الذي تريد الحصول على موضعه.

## الخطوة 3: الحصول على خصائص تحديد موضع المصفوفة
بعد ذلك، سوف نتحقق من نوع موضع المصفوفة ونحصل على خصائص الموضع المناسبة. استخدم الكود التالي:

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

 نستخدم هنا شرطًا للتحقق مما إذا كانت المصفوفة من النوع العائم. إذا كان الأمر كذلك، فإننا نطبع`RelativeHorizontalAlignment` و`RelativeVerticalAlignment` للحصول على المحاذاة الأفقية والرأسية النسبية للجدول. وإلا فإننا نطبع`Alignment` الخاصية للحصول على محاذاة الصفيف.

### نموذج التعليمات البرمجية المصدر للحصول على موضع الجدول باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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
في هذا البرنامج التعليمي، تعلمنا كيفية تحديد موضع الجدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك الحصول على خصائص تحديد موضع الجدول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تحليل المصفوفات ومعالجتها وفقًا لمواضعها المحددة.