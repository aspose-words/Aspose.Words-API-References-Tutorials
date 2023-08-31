---
title: تحويل إلى خلايا مدمجة أفقيا
linktitle: تحويل إلى خلايا مدمجة أفقيا
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Words لـ .NET لتحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word. سنتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي، ستكون قادرًا على التعامل مع خلايا الجدول في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم بإضافة مرجع إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء معالجة الكلمات بالجدول، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Table with merged cells.docx");

// الوصول إلى المصفوفة
Table table = doc.FirstSection.Body.Tables[0];
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك. تأكد أيضًا من أن المستند يحتوي على جدول يحتوي على خلايا مدمجة أفقيًا.

## الخطوة 3: التحويل إلى الخلايا المدمجة أفقيًا
 بعد ذلك، سنقوم بتحويل خلايا الجدول إلى خلايا مدمجة أفقيًا باستخدام الأمر`ConvertToHorizontallyMergedCells()` طريقة. استخدم الكود التالي:

```csharp
// تحويل إلى خلايا مدمجة أفقيا
table. ConvertToHorizontallyMergedCells();
```

 هنا ندعو فقط`ConvertToHorizontallyMergedCells()` الطريقة على المصفوفة لإجراء التحويل.

### نموذج التعليمات البرمجية المصدر للتحويل إلى الخلايا المدمجة أفقيًا باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// الآن تحتوي الخلايا المدمجة على علامات دمج مناسبة.
	table.ConvertToHorizontallyMergedCells();
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك التعامل مع خلايا الجدول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة إدارة وتنظيم بياناتك بطريقة مرنة وشخصية في جدول.