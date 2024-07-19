---
title: جدول متداخل
linktitle: جدول متداخل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/nested-table/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على إنشاء جداول متداخلة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستندات
لبدء معالجة الكلمات باستخدام منشئ المستندات والمستندات، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document doc = new Document();

// تهيئة منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: بناء الجدول المتداخل
بعد ذلك، سنقوم ببناء الجدول المتداخل عن طريق إدراج خلايا في الجدول الخارجي وإنشاء جدول جديد داخل الخلية الأولى. استخدم الكود التالي:

```csharp
// أدخل الخلية الأولى من الجدول الخارجي
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// أدخل الخلية الثانية من الجدول الخارجي
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// إنهاء الجدول الخارجي
builder. EndTable();

// الانتقال إلى الخلية الأولى من الجدول الخارجي
builder.MoveTo(cell.FirstParagraph);

// بناء الجدول الداخلي
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// نهاية الجدول الداخلي
builder. EndTable();
```

نستخدم هنا أداة إنشاء المستندات لإدراج الخلايا والمحتوى في الجدول الخارجي. ثم ننقل مؤشر أداة إنشاء المستندات إلى الخلية الأولى في الجدول الخارجي وننشئ جدولًا جديدًا بالداخل عن طريق إدراج الخلايا والمحتوى.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بالجدول المتداخل. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر للجدول المتداخل باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// هذا الاستدعاء مهم لإنشاء جدول متداخل داخل الجدول الأول.
	//بدون هذا الاستدعاء، سيتم إلحاق الخلايا المدرجة أدناه بالجدول الخارجي.
	builder.EndTable();
	// الانتقال إلى الخلية الأولى من الجدول الخارجي.
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
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء جدول متداخل في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك إنشاء جداول متداخلة وفقًا لاحتياجاتك المحددة في مستندات Word الخاصة بك برمجيًا.
