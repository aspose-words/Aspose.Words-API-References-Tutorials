---
title: أقحم الصور
linktitle: أقحم الصور
second_title: Aspose.Words لمراجع .NET API
description: دليل مفصّل خطوة بخطوة لتمكين استيفاء الصور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/interpolate-images/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة الاستيفاء للصور مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية تمكين استيفاء الصور عند التحويل إلى PDF.

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

## الخطوة 3: قم بتكوين خيارات الحفظ بتنسيق PDF باستخدام إطار الإقحام

 لتمكين استيفاء الصور عند التحويل إلى PDF ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن عن طريق تعيين`InterpolateImages` ملكية ل`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## الخطوة 4: احفظ المستند كملف PDF مع استيفاء الإطار

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تمكين استيفاء الصور أثناء تحويل مستند إلى PDF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لاستيفاء الصورة باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
