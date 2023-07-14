---
title: تحديث خاصية آخر مطبوعة في مستند PDF
linktitle: تحديث خاصية آخر مطبوعة في مستند PDF
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لتحديث خاصية "آخر طباعة" عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام خاصية "آخر طباعة" في ميزة تحديث مستند PDF باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية تكوين خيار تحديث خاصية "آخر طباعة" عند التحويل إلى PDF.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "Rendering.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات حفظ كملف PDF مع خاصية "آخر طباعة" محدثة

 لتمكين تحديث خاصية "Last Printed" عند التحويل إلى PDF ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن وتعيين`UpdateLastPrintedProperty` ملكية ل`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## الخطوة 4: احفظ المستند بتنسيق PDF مع تحديث خاصية "آخر طباعة"

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تمكين تحديث خاصية "آخر طباعة" عند تحويل مستند إلى PDF باستخدام Aspose.Words for .NET.

### مثال على كود المصدر لتحديث خاصية "الطباعة الأخيرة" باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات المحددة ، يمكنك بسهولة تكوين خيار تحديث خاصية "آخر طباعة" عند تحويل مستند إلى PDF. استخدم هذه الميزة لتتبع استخدام المستند والمعلومات ذات الصلة.

### أسئلة مكررة

#### س: ما هي خاصية "آخر طباعة" في مستند PDF؟
ج: تشير خاصية "آخر طباعة" في مستند PDF إلى تاريخ ووقت آخر طباعة للمستند. يمكن أن تكون هذه الخاصية مفيدة لتتبع المعلومات حول استخدام المستند وإدارته.

#### س: كيف يمكنني تحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتحديث خاصية "آخر طباعة" في مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بإنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 قم بإنشاء مثيل لـ`PdfSaveOptions`فئة وضبط`UpdateLastPrintedProperty` ملكية ل`true` لتمكين تحديث خاصية "آخر مطبوعة".

 استخدم ال`Save` طريقة`Document`class لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: كيف يمكنني التحقق مما إذا كانت خاصية "آخر طباعة" قد تم تحديثها في مستند PDF الذي تم إنشاؤه؟
ج: يمكنك التحقق مما إذا كانت خاصية "آخر طباعة" قد تم تحديثها في مستند PDF الذي تم إنشاؤه عن طريق فتح ملف PDF باستخدام عارض PDF متوافق ، مثل Adobe Acrobat Reader وعرض معلومات المستند. يجب أن يتوافق تاريخ ووقت آخر طباعة مع تاريخ ووقت إنشاء مستند PDF.
