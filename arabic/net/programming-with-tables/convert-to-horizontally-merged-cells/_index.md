---
title: تحويل إلى خلايا مدمجة أفقيًا
linktitle: تحويل إلى خلايا مدمجة أفقيًا
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخدام Aspose.Words for .NET لتحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word. سوف نتبع دليلًا خطوة بخطوة لفهم الكود وتنفيذ هذه الميزة. في نهاية هذا البرنامج التعليمي ، ستتمكن من معالجة خلايا الجدول في مستندات Word الخاصة بك برمجيًا.

## الخطوة 1: إعداد المشروع
1. قم بتشغيل Visual Studio وإنشاء مشروع C # جديد.
2. أضف مرجعًا إلى مكتبة Aspose.Words for .NET.

## الخطوة 2: تحميل المستند والوصول إلى الجدول
لبدء العمل مع الجدول ، نحتاج إلى تحميل المستند الذي يحتوي عليه والوصول إليه. اتبع هذه الخطوات:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Table with merged cells.docx");

// الوصول إلى المصفوفة
Table table = doc.FirstSection.Body.Tables[0];
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات. تأكد أيضًا من أن المستند يحتوي على جدول به خلايا مدمجة أفقيًا.

## الخطوة 3: التحويل إلى خلايا مدمجة أفقيًا
 بعد ذلك ، سنقوم بتحويل خلايا الجدول إلى خلايا مدمجة أفقيًا باستخدام الامتداد`ConvertToHorizontallyMergedCells()` طريقة. استخدم الكود التالي:

```csharp
// التحويل إلى خلايا مدمجة أفقيًا
table. ConvertToHorizontallyMergedCells();
```

 هنا فقط نسمي`ConvertToHorizontallyMergedCells()` الطريقة على المصفوفة لإجراء التحويل.

### عينة من التعليمات البرمجية المصدر للتحويل إلى خلايا مدمجة أفقيًا باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// تحتوي الخلايا المدمجة الآن على أعلام دمج مناسبة.
	table.ConvertToHorizontallyMergedCells();
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل خلايا الجدول إلى خلايا مدمجة أفقيًا في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك معالجة خلايا الجدول في مستندات Word الخاصة بك برمجيًا. تتيح لك هذه الميزة إدارة وتنظيم بياناتك بطريقة مرنة ومخصصة في جدول.