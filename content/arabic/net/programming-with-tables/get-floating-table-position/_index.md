---
title: الحصول على موقف الجدول العائم
linktitle: الحصول على موقف الجدول العائم
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية الحصول على موضع الجداول العائمة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/get-floating-table-position/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية الحصول على موضع الجدول العائم في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من الحصول على خصائص تحديد الموضع للجدول العائم في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند والوصول إلى الجداول
لبدء معالجة الكلمات باستخدام الجداول ، نحتاج إلى تحميل المستند الذي يحتوي عليها والوصول إليها. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات. تأكد أيضًا من أن المستند يحتوي على جداول عائمة.

## الخطوة 3: الحصول على خصائص تحديد موضع الجدول العائم
بعد ذلك ، سنقوم بتكرار جميع الجداول الموجودة في المستند والحصول على خصائص تحديد موضع الجدول العائم. استخدم الكود التالي:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// إذا كانت المصفوفة من النوع العائم ، فقم بطباعة خصائص تحديد الموضع الخاصة بها.
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

 نحن هنا نستخدم ملف`foreach` حلقة للتكرار خلال جميع المصفوفات في المستند. نتحقق مما إذا كانت المصفوفة من النوع العائم عن طريق التحقق من`TextWrapping` ملكية. إذا كان الأمر كذلك ، فإننا نطبع خصائص تحديد موضع الجدول ، مثل المرساة الأفقية ، والمثبت الرأسي ، والمسافات الأفقية والرأسية المطلقة ، والإذن المتداخل ، والمسافة الأفقية المطلقة ، والمحاذاة الرأسية النسبية.
 
### نموذج التعليمات البرمجية المصدر للحصول على موقع الجدول العائم باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// إذا كان الجدول من النوع العائم ، فقم بطباعة خصائص تحديد الموضع الخاصة به.
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
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على موضع الجدول العائم في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك الحصول على خصائص تحديد موضع الجداول العائمة في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تحليل الجداول العائمة ومعالجتها وفقًا لاحتياجاتك الخاصة.