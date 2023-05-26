---
title: احتواء تلقائي للجدول مع المحتويات
linktitle: احتواء تلقائي للجدول مع المحتويات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ملاءمة الجدول تلقائيًا لمحتوياته في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/auto-fit-table-to-contents/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لملاءمة جدول تلقائيًا مع محتوياته في مستند Word باستخدام C #. سنمر بعملية كتابة التعليمات البرمجية خطوة بخطوة لتحقيق هذه الوظيفة. بنهاية هذا البرنامج التعليمي ، سيكون لديك فهم واضح لكيفية التعامل مع الجداول في مستندات Word برمجيًا.

## الخطوة 1: قم بإعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: قم بتحميل مستند Word
لبدء العمل مع الجدول ، نحتاج إلى تحميل مستند Word الذي يحتوي على الجدول. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

//قم بتحميل مستند Word
Document doc = new Document(dataDir + "Tables.docx");
```

تأكد من استبدال "دليل المستند" بالمسار الفعلي إلى المستند.

## الخطوة 3: الوصول إلى الجدول وضبطه تلقائيًا مع المحتويات
بعد ذلك ، نحتاج إلى الوصول إلى الجدول داخل المستند وتطبيق سلوك الاحتواء التلقائي. استخدم الكود التالي:

```csharp
// الوصول إلى الجدول
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// احتواء الجدول تلقائيًا مع محتوياته
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 هنا ، نقوم بإلقاء أول عقدة فرعية من النوع`Table` من المستند ثم استخدام امتداد`AutoFit` الطريقة مع`AutoFitToContents` لضبط عرض الجدول ليلائم محتواه.

## الخطوة 4: احفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل بالجدول المجهز تلقائيًا. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر لـ Auto Fit Table To Contents باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية ملاءمة الجدول تلقائيًا لمحتوياته في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك معالجة الجداول في مستندات Word برمجيًا. يتيح لك ذلك ضبط عرض الجدول ديناميكيًا بناءً على محتواه ، مما يوفر مستندًا أكثر احترافًا وجاذبية.