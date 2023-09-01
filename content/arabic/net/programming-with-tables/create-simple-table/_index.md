---
title: إنشاء جدول بسيط
linktitle: إنشاء جدول بسيط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/create-simple-table/
---

في هذا البرنامج التعليمي، سنتعلم كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستتمكن من إنشاء جداول مخصصة في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: إنشاء المستند وتهيئة منشئ المستندات
للبدء في إنشاء الجدول، نحتاج إلى إنشاء مستند جديد وتهيئة منشئ المستندات. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وتهيئة منشئ المستندات
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 3: بناء المصفوفة
بعد ذلك، سنقوم ببناء الجدول باستخدام الطرق التي يوفرها منشئ المستندات. استخدم الكود التالي:

```csharp
// البدء في بناء المصفوفة
builder. StartTable();

// بناء الخلية الأولى من الصف الأول
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// بناء الخلية الثانية من الصف الأول
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//اتصل بالطريقة التالية لإنهاء السطر الأول وبدء سطر جديد
builder. EndRow();

// بناء الخلية الأولى من الصف الثاني
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// بناء الخلية الثانية من الصف الثاني
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// استدعاء الطريقة التالية لإنهاء السطر الثاني
builder. EndRow();

// إشارة إلى الانتهاء من بناء الجدول
builder. EndTable();
```

 نستخدم هنا أداة إنشاء المستندات لبناء الجدول خطوة بخطوة. نبدأ بالدعوة`StartTable()` لتهيئة الجدول، ثم استخدم`InsertCell()` لإدراج الخلايا و`Write()` لإضافة محتوى إلى كل خلية. نحن نستخدم أيضا`EndRow()` لإنهاء صف وبدء صف جديد. وأخيرا ندعو`EndTable()` للإشارة إلى اكتمال بناء الجدول.

## الخطوة 4: احفظ المستند
وأخيرا، نحن بحاجة إلى الحفظ

  المستند الذي يحتوي على الجدول الذي تم إنشاؤه. استخدم الكود التالي:

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لإنشاء جدول بسيط باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// البدء في بناء الجدول.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// بناء الخلية الثانية.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// اتصل بالطريقة التالية لإنهاء الصف وبدء صف جديد.
	builder.EndRow();
	// بناء الخلية الأولى من الصف الثاني.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// بناء الخلية الثانية.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//إشارة إلى أننا انتهينا من بناء الجدول.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء جدول بسيط في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك إنشاء جداول مخصصة في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة تنسيق بياناتك وتنظيمها بطريقة منظمة وواضحة.