---
title: إنشاء جدول بسيط
linktitle: إنشاء جدول بسيط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/create-simple-table/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من إنشاء جداول مخصصة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستند
لبدء بناء الجدول ، نحتاج إلى إنشاء مستند جديد وتهيئة منشئ المستندات. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وتهيئة منشئ المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: بناء المصفوفة
بعد ذلك ، سنبني الجدول باستخدام الطرق التي يوفرها منشئ المستندات. استخدم الكود التالي:

```csharp
// ابدأ بناء المصفوفة
builder. StartTable();

// بناء الخلية الأولى من الصف الأول
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// بناء الخلية الثانية من الصف الأول
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//اتصل بالطريقة التالية لإنهاء السطر الأول وبدء سطر جديد
builder. EndRow();

// بناء الخلية الأولى للصف الثاني
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// بناء الخلية الثانية للصف الثاني
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// اتصل بالطريقة التالية لإنهاء السطر الثاني
builder. EndRow();

// الإشارة إلى أن بناء الجدول قد اكتمل
builder. EndTable();
```

 هنا نستخدم منشئ المستندات لبناء الجدول خطوة بخطوة. نبدأ بالاتصال`StartTable()` لتهيئة الجدول ، ثم استخدم`InsertCell()` لإدراج الخلايا و`Write()` لإضافة محتوى إلى كل خلية. نحن نستخدم أيضا`EndRow()` لإنهاء صف وبدء صف جديد. أخيرا ، نحن ندعو`EndTable()` للإشارة إلى اكتمال بناء الجدول.

## الخطوة 4: احفظ المستند
أخيرًا ، نحن بحاجة إلى الحفظ

  المستند مع الجدول الذي تم إنشاؤه. استخدم الكود التالي:

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Create Simple Table باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// ابدأ في بناء الطاولة.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// قم ببناء الخلية الثانية.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// اتصل بالطريقة التالية لإنهاء الصف وبدء صف جديد.
	builder.EndRow();
	// قم ببناء الخلية الأولى من الصف الثاني.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// قم ببناء الخلية الثانية.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//إشارة إلى أننا انتهينا من بناء الطاولة.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ رمز C # المقدم ، يمكنك إنشاء جداول مخصصة في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تنسيق بياناتك وتنظيمها بطريقة منظمة وواضحة.