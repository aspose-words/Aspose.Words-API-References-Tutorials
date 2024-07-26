---
title: استنساخ الجدول الكامل
linktitle: استنساخ الجدول الكامل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استنساخ جدول بأكمله في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/clone-complete-table/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لاستنساخ جدول كامل في مستند Word. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من استنساخ الجداول في مستندات Word الخاصة بك برمجيًا.

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

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: استنساخ المصفوفة الكاملة
بعد ذلك، سنقوم باستنساخ الجدول بأكمله وإدراجه في المستند بعد المستند الأصلي. استخدم الكود التالي:

```csharp
// استنساخ المصفوفة
Table tableClone = (Table)table.Clone(true);

// أدخل الجدول المستنسخ في المستند بعد المستند الأصلي
table.ParentNode.InsertAfter(tableClone, table);

// أدخل فقرة فارغة بين الجدولين
// وإلا فسيتم دمجها في واحدة عند الحفظ (وهذا بسبب التحقق من صحة الوثيقة)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 نحن هنا نستخدم`Clone` طريقة لإنشاء نسخة كاملة من المصفوفة. ثم نستخدم`InsertAfter` لإدراج الجدول المستنسخ في المستند، بعد الجدول الأصلي. نقوم أيضًا بإضافة فقرة فارغة بين الجدولين لمنع دمجهما عند الحفظ.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بالجدول المستنسخ. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.
  
### نموذج التعليمات البرمجية المصدر لـ Clone Complete Table باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// انسخ الجدول وأدخله في المستند بعد المستند الأصلي.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// أدخل فقرة فارغة بين الجدولين،
	// وإلا فسيتم دمجها في واحدة عند حفظها، وهذا يتعلق بالتحقق من صحة المستند.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استنساخ جدول بأكمله في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك استنساخ الجداول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة إجراء معالجات متقدمة على المصفوفات لتناسب احتياجاتك الخاصة.