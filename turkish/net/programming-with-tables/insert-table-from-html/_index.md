---
title: إدراج جدول من Html
linktitle: إدراج جدول من Html
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج جدول من HTML في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-from-html/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إدراج جدول في مستند Word من HTML باستخدام Aspose.Words for .NET. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بنهاية هذا البرنامج التعليمي ، ستتمكن من إدراج جداول من HTML في مستندات Word برمجيًا.

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

## الخطوة 3: إدراج الجدول من HTML
بعد ذلك ، سنقوم بإدخال الجدول في المستند باستخدام كود HTML. استخدم الكود التالي:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 هنا نستخدم ملف`InsertHtml` طريقة منشئ المستند لإدراج HTML الذي يحتوي على الجدول. ينشئ HTML المحدد جدولًا من صفين وخليتين في كل صف. يمكنك تخصيص محتوى الجدول عن طريق تعديل كود HTML وفقًا لاحتياجاتك.

## الخطوة 4: حفظ المستند المعدل
أخيرًا ، نحتاج إلى حفظ المستند المعدل مع إدراج الجدول من HTML. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لـ Insert Table From Html باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// لاحظ أن AutoFitSettings لا ينطبق على الجداول المدرجة من HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إدراج جدول في مستند Word من HTML باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إدراج جداول من HTML في مستندات Word برمجيًا. تتيح لك هذه الميزة تحويل واستيراد البيانات الجدولية من مصادر HTML إلى مستندات Word الخاصة بك.
