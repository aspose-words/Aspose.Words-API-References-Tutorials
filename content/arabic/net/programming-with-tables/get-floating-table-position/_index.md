---
title: الحصول على موضع الجدول العائم
linktitle: الحصول على موضع الجدول العائم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد موضع الجداول العائمة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/get-floating-table-position/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية تحديد موضع الجدول العائم في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من الحصول على خصائص تحديد موضع الجدول العائم في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجداول
لبدء معالجة الكلمات بالجداول، نحتاج إلى تحميل المستند الذي يحتوي عليها والوصول إليها. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك. تأكد أيضًا من أن المستند يحتوي على جداول عائمة.

## الخطوة 3: الحصول على خصائص تحديد موضع الجدول العائم
بعد ذلك، سنقوم بمراجعة كافة الجداول الموجودة في المستند والحصول على خصائص موضع الجدول العائم. استخدم الكود التالي:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// إذا كان المصفوفة من النوع العائم، فاطبع خصائص تحديد موضعها.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 نحن هنا نستخدم أ`foreach` حلقة للتكرار عبر كافة المصفوفات الموجودة في المستند. نتحقق مما إذا كانت المصفوفة من النوع العائم عن طريق التحقق من`TextWrapping` ملكية. إذا كان الأمر كذلك، فإننا نطبع خصائص تحديد موضع الجدول، مثل الارتساء الأفقي، والارتساء الرأسي، والمسافات الأفقية والرأسية المطلقة، وإذن التداخل، والمسافة الأفقية المطلقة، والمحاذاة الرأسية النسبية.
 
### نموذج التعليمات البرمجية المصدر للحصول على موضع الجدول العائم باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// إذا كان الجدول عائمًا، فقم بطباعة خصائص تحديد موضعه.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على موضع الجدول العائم في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك الحصول على خصائص تحديد موضع الجداول العائمة في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تحليل الجداول العائمة ومعالجتها وفقًا لاحتياجاتك المحددة.