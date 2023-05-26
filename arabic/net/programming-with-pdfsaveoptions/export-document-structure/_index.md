---
title: تصدير هيكل الوثيقة
linktitle: تصدير هيكل الوثيقة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتصدير بنية المستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/export-document-structure/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة بنية مستند التصدير مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية تصدير بنية المستند وإنشاء ملف PDF بهيكل المستند المرئي.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "Paragraphs.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## الخطوة 3: تكوين خيارات الحفظ كملف PDF

 لتصدير بنية المستند وجعل الهيكل مرئيًا في جزء التنقل "المحتوى" في Adobe Acrobat Pro أثناء تحرير ملف PDF ، نحتاج إلى تكوين`PdfSaveOptions` كائن مع`ExportDocumentStructure` تعيين الخاصية على`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## الخطوة 4: احفظ المستند كملف PDF بهيكل المستند

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تصدير بنية المستند وإنشاء ملف PDF بهيكل المستند المرئي باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لتصدير بنية المستند باستخدام Aspose.Words for .NET


```csharp

            // المسار إلى دليل المستندات.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // سيتم زيادة حجم الملف وستظهر البنية في جزء التنقل "المحتوى"
            // Adobe Acrobat Pro ، أثناء تحرير ملف .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
