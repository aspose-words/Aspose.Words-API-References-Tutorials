---
title: تصدير الإشارات المرجعية لتذييل رأس المستند Word إلى مستند PDF
linktitle: تصدير الإشارات المرجعية لتذييل رأس المستند Word إلى مستند PDF
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لتصدير إشارات مرجعية في ترويسة مستند Word إلى إشارات مرجعية لمستند pdf باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية تصدير إشارات مرجعية في تذييل مستند Word إلى ميزة مستند pdf باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تصدير الإشارات المرجعية من رؤوس الصفحات وتذييلاتها في المستند وإنشاء ملف PDF بالإشارات المرجعية المناسبة.

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

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية تصدير الإشارات المرجعية للرأس والتذييل من مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET. تسمح الإشارات المرجعية المصدرة بالتنقل السهل والإشارة السريعة إلى الرؤوس والتذييلات المقابلة في مستند PDF الذي تم إنشاؤه. اتبع الخطوات الموضحة لتصدير الإشارات المرجعية للرأس والتذييل من مستند وإنشاء ملف PDF مع الإشارات المرجعية المناسبة باستخدام Aspose.Words for .NET. تأكد من تحديد المسار الصحيح لمستنداتك وتكوين خيارات الحفظ حسب الحاجة.

# أسئلة مكررة

### س: ما هو تصدير الإشارات المرجعية للرأس والتذييل من مستند Word إلى مستند PDF؟
ج: يعد تصدير الإشارات المرجعية للرأس والتذييل من مستند Word إلى مستند PDF ميزة للاحتفاظ بالإشارات المرجعية وإنشاؤها في مستند PDF من الرؤوس والتذييلات. تذييل مستند Word الأصلي. يتيح ذلك للمستخدمين التنقل بسرعة وسهولة عبر مستند PDF باستخدام الإشارات المرجعية المقابلة للرؤوس والتذييلات.

### س: كيف يمكنني استخدام Aspose.Words for .NET لتصدير الإشارات المرجعية للرأس والتذييل من مستند Word إلى مستند PDF؟
ج: لتصدير الإشارات المرجعية للرأس والتذييل من مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل المستند الذي تريد معالجته باستخدام ملف`Document` class وحدد المسار إلى مستند Word في دليل المستندات المحدد.

 قم بتكوين حفظ كخيارات PDF عن طريق إنشاء مثيل لملف`PdfSaveOptions` فئة وتعيين خيارات إشارة الرأس والتذييل المناسبة.

 احفظ المستند بتنسيق PDF باستخدام ملف`Save` طريقة`Document`فئة تحدد المسار وخيارات الحفظ.

### س: ما هي فوائد تصدير الإشارات المرجعية للرأس والتذييل إلى مستند PDF؟
ج: مزايا تصدير الإشارات المرجعية للرأس والتذييل إلى مستند PDF هي:

سهولة التنقل: تتيح الإشارات المرجعية للمستخدمين التنقل بسهولة في مستند PDF من خلال الرجوع إلى رؤوس وتذييلات معينة.

المرجع السريع: تسمح الإشارات المرجعية للمستخدمين بالعثور بسرعة على الأقسام ذات الصلة من مستند PDF استنادًا إلى الرؤوس والتذييلات.