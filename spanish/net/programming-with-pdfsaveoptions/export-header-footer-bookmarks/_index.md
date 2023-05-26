---
title: تصدير الإشارات المرجعية في رأس تذييل الصفحة
linktitle: تصدير الإشارات المرجعية في رأس تذييل الصفحة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتصدير الإشارات المرجعية في الرأس والتذييل باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة إشارات مرجعية لرأس وتذييل الصفحة مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تصدير الإشارات المرجعية من رؤوس الصفحات وتذييلاتها في المستند وإنشاء ملف PDF بالإشارات المرجعية المناسبة.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن الوثيقة تسمى "Bookmarks in headers and footers.docx" وهي موجودة في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## الخطوة 3: تكوين خيارات الحفظ كملف PDF

 لتصدير الإشارات المرجعية للرأس والتذييل ، نحتاج إلى تكوين ملف`PdfSaveOptions` هدف. في هذا المثال ، قمنا بتعيين مستوى مخطط الإشارة المرجعية الافتراضي على 1 ووضع تصدير الإشارة المرجعية للرأس والتذييل على "الأول".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## الخطوة 4: احفظ المستند كملف PDF مع الإشارات المرجعية للرؤوس والتذييلات

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تصدير إشارات مرجعية للرأس والتذييل من مستند وإنشاء ملف PDF مع الإشارات المرجعية المناسبة باستخدام Aspose.Words for .NET.

### عينة من التعليمات البرمجية المصدر لتصدير الإشارات المرجعية في الرأس والتذييل باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
