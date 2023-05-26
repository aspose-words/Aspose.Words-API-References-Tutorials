---
title: استنساخ الجدول الكامل
linktitle: استنساخ الجدول الكامل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استنساخ جدول كامل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/clone-complete-table/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لاستنساخ جدول كامل في مستند Word. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من استنساخ الجداول في مستندات Word برمجيًا.

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

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: استنساخ الصفيف الكامل
بعد ذلك ، سنقوم باستنساخ الجدول بأكمله وإدخاله في المستند بعد المستند الأصلي. استخدم الكود التالي:

```csharp
// استنساخ المصفوفة
Table tableClone = (Table)table.Clone(true);

// أدخل الجدول المستنسخ في المستند بعد المستند الأصلي
table.ParentNode.InsertAfter(tableClone, table);

// أدخل فقرة فارغة بين الجدولين
// وإلا سيتم دمجها في واحدة عند الحفظ (هذا بسبب التحقق من صحة المستند)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 نحن هنا نستخدم ملف`Clone` طريقة لإنشاء نسخة كاملة من المصفوفة. ثم نستخدم`InsertAfter` لإدراج الجدول المستنسخ في المستند ، بعد الجدول الأصلي. نضيف أيضًا فقرة فارغة بين الجدولين لمنع دمجهما عند الحفظ.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل بالجدول المستنسخ. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.
  
### نموذج التعليمات البرمجية المصدر لـ Clone Complete Table باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// انسخ الجدول وأدخله في المستند بعد المستند الأصلي.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// أدخل فقرة فارغة بين الجدولين ،
	//وإلا سيتم دمجها في واحدة عند حفظ هذا له علاقة بالتحقق من صحة المستند.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية استنساخ جدول كامل في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك استنساخ الجداول في مستندات Word برمجيًا. تتيح لك هذه الميزة إجراء معالجات متقدمة على المصفوفات لتناسب احتياجاتك الخاصة.