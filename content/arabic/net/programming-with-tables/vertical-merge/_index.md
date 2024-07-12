---
title: دمج عمودي
linktitle: دمج عمودي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية دمج الخلايا رأسيًا في جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/vertical-merge/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية دمج الخلايا رأسيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من دمج الخلايا عموديًا في جداولك في مستندات Word.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل الوثيقة
لبدء معالجة الكلمات مع المستند، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء مستند جديد
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: دمج الخلايا عموديًا
بعد ذلك سنقوم بدمج الخلايا عموديًا في الجدول. استخدم الكود التالي:

```csharp
// أدخل خلية
builder. InsertCell();

// قم بتطبيق الدمج العمودي على الخلية الأولى
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// أدخل خلية أخرى
builder. InsertCell();

// لا يتم تطبيق أي دمج رأسي على الخلية
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// أدخل خلية
builder. InsertCell();

// قم بتطبيق الدمج العمودي مع الخلية السابقة
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// أدخل خلية أخرى
builder. InsertCell();

// لا يتم تطبيق أي دمج رأسي على الخلية
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//إنهاء إنشاء الجدول
builder. EndTable();
```

في هذا الكود، نستخدم منشئ DocumentBuilder لإدراج الخلايا في الجدول. نحن نطبق الدمج الرأسي على الخلايا باستخدام خاصية CellFormat.VerticalMerge. نستخدم CellMerge.First لدمج الخلية الأولى، وCellMerge.Previous للدمج مع الخلية السابقة، وCellMerge.None لعدم الدمج العمودي.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بالخلايا المدمجة. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر للدمج العمودي باستخدام Aspose.Words لـ .NET 
```csharp
	// المسار إلى دليل المستندات الخاص بك
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
	// يتم دمج هذه الخلية عموديًا مع الخلية الموجودة أعلاه ويجب أن تكون فارغة.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية دمج الخلايا رأسيًا في جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك بسهولة دمج الخلايا عموديًا في جداولك.