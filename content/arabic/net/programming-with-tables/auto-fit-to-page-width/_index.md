---
title: الملاءمة التلقائية لعرض الصفحة
linktitle: الملاءمة التلقائية لعرض الصفحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الملاءمة التلقائية للجدول مع عرض الصفحة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/auto-fit-to-page-width/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Words for .NET لملاءمة الجدول تلقائيًا مع عرض الصفحة في مستند Word. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستكون قادرًا على التعامل مع الجداول في مستندات Word برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء وتكوين المستند
لبدء معالجة الكلمات بالجدول، نحتاج إلى إنشاء مستند وتكوين منشئ المستندات. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند ومولد المستندات
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: إدراج الجدول وتكوينه
بعد ذلك، سنقوم بإدراج جدول في المستند بعرض يغطي نصف عرض الصفحة. استخدم الكود التالي:

```csharp
// أدخل الجدول وقم بتكوين عرضه
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

نستخدم هنا أداة إنشاء المستندات لبدء إنشاء الجدول وإدراج الخلايا وضبط العرض المفضل للجدول على 50% من عرض الصفحة. ثم نقوم بإضافة نص في كل خلية.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل مع تعديل الجدول حسب عرض الصفحة. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.
  
### نموذج التعليمات البرمجية المصدر للاحتواء التلقائي لعرض الصفحة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// قم بإدراج جدول بعرض يستهلك نصف عرض الصفحة.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية الملاءمة التلقائية للجدول مع عرض الصفحة في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك التعامل مع الجداول في مستندات Word الخاصة بك برمجيًا. تسمح لك هذه الميزة بتعديل عرض الجدول ديناميكيًا وفقًا للصفحة، وبالتالي تقديم وثيقة احترافية وجذابة بصريًا.