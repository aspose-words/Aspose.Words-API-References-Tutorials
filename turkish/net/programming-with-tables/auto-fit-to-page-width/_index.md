---
title: احتواء تلقائي لعرض الصفحة
linktitle: احتواء تلقائي لعرض الصفحة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ملاءمة جدول تلقائيًا لعرض الصفحة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/auto-fit-to-page-width/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لملاءمة جدول تلقائيًا لعرض الصفحة في مستند Word. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من معالجة الجداول في مستندات Word برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء وتكوين المستند
لبدء العمل مع الجدول ، نحتاج إلى إنشاء مستند وتكوين منشئ المستندات. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بإنشاء المستند ومُنشئ المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: إدخال الجدول وتكوينه
بعد ذلك ، سنقوم بإدراج جدول في المستند بعرض يشغل نصف عرض الصفحة. استخدم الكود التالي:

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

هنا نستخدم أداة إنشاء المستندات لبدء إنشاء الجدول وإدراج الخلايا وتعيين العرض المفضل للجدول على 50٪ من عرض الصفحة. ثم نضيف نصًا في كل خلية.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع تعديل الجدول حسب عرض الصفحة. استخدم الكود التالي:

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.
  
### عينة من التعليمات البرمجية المصدر لـ Auto Fit To Page Width باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// قم بإدراج جدول بعرض يشغل نصف عرض الصفحة.
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
في هذا البرنامج التعليمي ، تعلمنا كيفية ملاءمة جدول لعرض الصفحة تلقائيًا في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك معالجة الجداول في مستندات Word برمجيًا. تتيح لك هذه الميزة تكييف عرض الجدول ديناميكيًا وفقًا للصفحة ، وبالتالي تقديم مستند احترافي وجذاب بصريًا.