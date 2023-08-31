---
title: دمج عمودي
linktitle: دمج عمودي
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية الدمج الرأسي للخلايا في جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/vertical-merge/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية دمج الخلايا رأسيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من دمج الخلايا عموديًا في الجداول الخاصة بك في مستندات Word.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة الثانية: تحميل المستند
لبدء معالجة الكلمات بالمستند ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند جديد
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: دمج الخلايا عموديًا
بعد ذلك سنقوم بدمج الخلايا عموديًا في الجدول. استخدم الكود التالي:

```csharp
// أدخل خلية
builder. InsertCell();

// تطبيق الدمج العمودي على الخلية الأولى
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// أدخل خلية أخرى
builder. InsertCell();

// لا تطبق أي دمج عمودي على الخلية
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// أدخل خلية
builder. InsertCell();

// تطبيق الدمج العمودي مع الخلية السابقة
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// أدخل خلية أخرى
builder. InsertCell();

// لا تطبق أي دمج عمودي على الخلية
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//قم بإنهاء إنشاء الجدول
builder. EndTable();
```

في هذا الكود ، نستخدم مُنشئ DocumentBuilder لإدراج خلايا في جدول. نقوم بتطبيق الدمج الرأسي على الخلايا باستخدام خاصية CellFormat.VerticalMerge. نستخدم CellMerge ، أولًا لدمج الخلايا الأول ، CellMerge. سابقًا للدمج مع الخلية السابقة ، و CellMerge. لا يوجد أي دمج رأسي.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع الخلايا المدمجة. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### عينة من التعليمات البرمجية المصدر لـ Vertical Merge باستخدام Aspose.Words for .NET 
```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// تم دمج هذه الخلية عموديًا في الخلية أعلاه ويجب أن تكون فارغة.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية دمج الخلايا رأسيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك بسهولة دمج الخلايا العمودي في الجداول الخاصة بك.