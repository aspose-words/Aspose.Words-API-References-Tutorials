---
title: تحديث آخر خاصية مطبوعة في مستند PDF
linktitle: تحديث آخر خاصية مطبوعة في مستند PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحديث خاصية "آخر طباعة" عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام خاصية "الطباعة الأخيرة" في ميزة تحديث مستند PDF مع Aspose.Words for .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية تكوين خيار تحديث خاصية "آخر طباعة" عند التحويل إلى PDF.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء، تحتاج إلى تحديد المسار إلى الدليل الذي توجد به مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة

بعد ذلك، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال، نفترض أن المستند يسمى "Rendering.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: قم بتكوين خيارات الحفظ بتنسيق PDF مع خاصية "آخر طباعة" محدثة

 لتمكين تحديث خاصية "آخر طباعة" عند التحويل إلى PDF، نحتاج إلى تكوين`PdfSaveOptions` الكائن وتعيين`UpdateLastPrintedProperty`الملكية ل`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## الخطوة 4: احفظ المستند كملف PDF مع تحديث خاصية "آخر طباعة".

أخيرًا، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تمكين تحديث خاصية "آخر طباعة" عند تحويل مستند إلى PDF باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لتحديث خاصية "آخر طباعة" باستخدام Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات المذكورة، يمكنك بسهولة تكوين خيار تحديث خاصية "آخر طباعة" عند تحويل مستند إلى PDF. استخدم هذه الميزة لتتبع استخدام المستند والمعلومات ذات الصلة.

### أسئلة مكررة

#### س: ما هي خاصية "آخر طباعة" في مستند PDF؟
ج: تشير خاصية "آخر طباعة" في مستند PDF إلى تاريخ ووقت طباعة المستند آخر مرة. يمكن أن تكون هذه الخاصية مفيدة لتتبع المعلومات حول استخدام المستندات وإدارتها.

#### س: كيف يمكنني تحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 إنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 إنشاء مثيل لـ`PdfSaveOptions` فئة وتعيين`UpdateLastPrintedProperty`الملكية ل`true` لتمكين تحديث خاصية "آخر طباعة".

 استخدم ال`Save` طريقة`Document`فئة لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: كيف يمكنني التحقق من تحديث خاصية "آخر طباعة" في مستند PDF الذي تم إنشاؤه؟
ج: يمكنك التحقق من تحديث خاصية "آخر طباعة" في مستند PDF الذي تم إنشاؤه عن طريق فتح ملف PDF باستخدام عارض PDF متوافق، مثل Adobe Acrobat Reader، وعرض معلومات المستند. يجب أن يتوافق تاريخ ووقت آخر طباعة مع تاريخ ووقت إنشاء مستند PDF.
