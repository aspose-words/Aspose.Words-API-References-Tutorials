---
title: تحديث آخر خاصية مطبوعة
linktitle: تحديث آخر خاصية مطبوعة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتحديث خاصية "آخر طباعة" عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة تحديث خاصية "الطباعة الأخيرة" مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية تكوين خيار تحديث خاصية "آخر طباعة" عند التحويل إلى PDF.

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
