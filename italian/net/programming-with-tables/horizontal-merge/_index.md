---
title: دمج أفقي
linktitle: دمج أفقي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية دمج الخلايا أفقيًا في جدول Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/horizontal-merge/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية دمج الخلايا أفقيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من دمج الخلايا أفقيًا في جداول Word برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء العمل مع الجدول والخلايا ، نحتاج إلى إنشاء مستند جديد وتهيئة منشئ المستندات. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وتهيئة منشئ المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء الجدول مع الدمج الأفقي للخلايا
بعد ذلك ، سنبني الجدول ونطبق دمج الخلايا الأفقي باستخدام الخصائص التي توفرها Aspose.Words لـ .NET. استخدم الكود التالي:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// تم دمج هذه الخلية مع الخلية السابقة ويجب أن تكون فارغة.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 هنا نستخدم منشئ المستندات لبناء الجدول وتعيين خصائص الدمج الأفقي للخلية. نحن نستخدم ال`HorizontalMerge` ممتلكات`CellFormat` لتحديد نوع الدمج الأفقي المراد تطبيقه على كل خلية. استخدام`CellMerge.First` نقوم بدمج الخلية الأولى مع الأخرى التالية ، أثناء استخدام`CellMerge.Previous` نقوم بدمج الخلية الحالية مع الخلية السابقة.`CellMerge.None` يشير إلى أنه لا ينبغي دمج الخلية.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع دمج الخلايا أفقيًا. استخدم الكود التالي:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر للدمج الأفقي باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// تم دمج هذه الخلية مع الخلية السابقة ويجب أن تكون فارغة.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية دمج الخلايا أفقيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تطبيق دمج الخلايا الأفقية في جداول Word برمجيًا. تتيح لك هذه الميزة إنشاء تخطيطات جدول أكثر تعقيدًا وتنظيم بياناتك بشكل أفضل.