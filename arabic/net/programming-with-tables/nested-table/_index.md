---
title: جدول متداخل
linktitle: جدول متداخل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/nested-table/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من إنشاء جداول متداخلة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء العمل مع منشئ المستندات والمستندات ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// قم بتهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء الجدول المتداخل
بعد ذلك ، سنبني الجدول المتداخل عن طريق إدراج الخلايا في الجدول الخارجي وإنشاء جدول جديد داخل الخلية الأولى. استخدم الكود التالي:

```csharp
// أدخل الخلية الأولى من الجدول الخارجي
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// أدخل الخلية الثانية من الجدول الخارجي
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// إنهاء الجدول الخارجي
builder. EndTable();

// الانتقال إلى الخلية الأولى في الجدول الخارجي
builder.MoveTo(cell.FirstParagraph);

// بناء الجدول الداخلي
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// نهاية الجدول الداخلي
builder. EndTable();
```

هنا نستخدم منشئ المستندات لإدراج الخلايا والمحتوى في الجدول الخارجي. ثم ننقل مؤشر منشئ المستندات إلى الخلية الأولى من الجدول الخارجي ونبني جدولًا جديدًا بداخله عن طريق إدراج الخلايا والمحتوى.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل بالجدول المتداخل. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

تأكد من تحديد المسار الصحيح وملف الاسم لمستند الإخراج.

### نموذج التعليمات البرمجية المصدر للجدول المتداخل باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// هذا الاستدعاء مهم لإنشاء جدول متداخل داخل الجدول الأول.
	// بدون هذا الاستدعاء ، سيتم إلحاق الخلايا المدرجة أدناه بالجدول الخارجي.
	builder.EndTable();
	// الانتقال إلى الخلية الأولى في الجدول الخارجي.
	builder.MoveTo(cell.FirstParagraph);
	// بناء الجدول الداخلي.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إنشاء جداول متداخلة وفقًا لاحتياجاتك الخاصة في مستندات Word الخاصة بك برمجيًا.
