---
title: ملاءمة الجدول تلقائيًا للمحتويات
linktitle: ملاءمة الجدول تلقائيًا للمحتويات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ملاءمة الجدول تلقائيًا لمحتوياته في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/auto-fit-table-to-contents/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Words for .NET لملاءمة جدول تلقائيًا مع محتوياته في مستند Word باستخدام C#. سنتابع عملية كتابة التعليمات البرمجية خطوة بخطوة لتحقيق هذه الوظيفة. بحلول نهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح لكيفية التعامل مع الجداول في مستندات Word برمجياً.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: قم بتحميل مستند Word
لبدء معالجة الكلمات بالجدول، نحتاج إلى تحميل مستند Word الذي يحتوي على الجدول. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند الوورد
Document doc = new Document(dataDir + "Tables.docx");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للمستند الخاص بك.

## الخطوة 3: الوصول إلى الجدول وملاءمته تلقائيًا للمحتويات
بعد ذلك، نحتاج إلى الوصول إلى الجدول داخل المستند وتطبيق سلوك الاحتواء التلقائي. استخدم الكود التالي:

```csharp
// الوصول إلى الجدول
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// ملاءمة الجدول تلقائيًا لمحتوياته
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 هنا، نقوم بإلقاء العقدة الفرعية الأولى من النوع`Table` من المستند ثم استخدم`AutoFit` الطريقة مع`AutoFitToContents` السلوك لضبط عرض الجدول ليناسب محتواه.

## الخطوة 4: احفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بالجدول المجهز تلقائيًا. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر للملاءمة التلقائية للجدول مع المحتويات باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ملاءمة الجدول تلقائيًا لمحتوياته في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك التعامل مع الجداول في مستندات Word الخاصة بك برمجيًا. يتيح لك ذلك ضبط عرض الجدول ديناميكيًا بناءً على محتواه، مما يوفر مستندًا أكثر احترافية وجاذبية بصريًا.