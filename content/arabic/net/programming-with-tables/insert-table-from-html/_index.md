---
title: إدراج جدول من HTML
linktitle: إدراج جدول من HTML
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج جدول من HTML في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/insert-table-from-html/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية إدراج جدول في مستند Word من HTML باستخدام Aspose.Words for .NET. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على إدراج جداول من HTML إلى مستندات Word الخاصة بك برمجيًا.

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

## الخطوة 3: إدراج الجدول من HTML
بعد ذلك، سنقوم بإدراج الجدول في المستند باستخدام كود HTML. استخدم الكود التالي:

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

 هنا نستخدم`InsertHtml` طريقة منشئ المستندات لإدراج HTML الذي يحتوي على الجدول. يقوم HTML المحدد بإنشاء جدول يحتوي على صفين وخليتين في كل صف. يمكنك تخصيص محتوى الجدول عن طريق تعديل كود HTML وفقًا لاحتياجاتك.

## الخطوة 4: حفظ المستند المعدل
أخيرًا، نحتاج إلى حفظ المستند المعدل بالجدول المدرج من HTML. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للمستند الناتج.

### نموذج التعليمات البرمجية المصدر لإدراج جدول من Html باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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
في هذا البرنامج التعليمي، تعلمنا كيفية إدراج جدول في مستند Word من HTML باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك إدراج جداول من HTML في مستندات Word الخاصة بك برمجيًا. تسمح لك هذه الميزة بتحويل واستيراد البيانات الجدولية من مصادر HTML إلى مستندات Word الخاصة بك.
