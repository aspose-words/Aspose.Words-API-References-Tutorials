---
title: تعيين خيارات المخطط التفصيلي
linktitle: تعيين خيارات المخطط التفصيلي
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتعيين خيارات المخطط التفصيلي في مستند PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/set-outline-options/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام خيارات المخطط التفصيلي المحددة لميزة حجم ملف التعريف باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تعيين خيارات المخطط التفصيلي في مستند وإنشاء ملف PDF باستخدام خيارات المخطط التفصيلية المقابلة.

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

## الخطوة 3: تكوين خيارات الحفظ كملف PDF مع خيارات الخطة

 لتعيين خيارات المخطط التفصيلي في ملف PDF الذي تم إنشاؤه ، نحتاج إلى تكوين ملف`PdfSaveOptions` هدف. يمكننا تعيين عدد مستويات مخطط العنوان (`HeadingsOutlineLevels`) وعدد مستويات المخطط التفصيلي الموسع (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## الخطوة 4: احفظ المستند بصيغة PDF مع خيارات المخطط التفصيلي

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تعيين خيارات المخطط التفصيلي في مستند وإنشاء ملف PDF مع خيارات المخطط التفصيلية المقابلة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لتعيين خيارات الخطة لحجم ملف التعريف باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
