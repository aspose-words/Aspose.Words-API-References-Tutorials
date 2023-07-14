---
title: عرض عنوان المستند في شريط عنوان النافذة
linktitle: عرض عنوان المستند في شريط عنوان النافذة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لعرض عنوان المستند في شريط عنوان النافذة باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة عرض عنوان المستند في شريط عنوان النافذة عند فتح مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تكوين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين عرض عنوان المستند في شريط عنوان النافذة:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

يتيح هذا الخيار عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لعرض عنوان المستند في شريط عناوين النافذة باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لعرض عنوان المستند في شريط عنوان النافذة في مستند PDF باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
باتباع هذه الخطوات ، يمكنك بسهولة عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.

### أسئلة مكررة

#### س: ما هي ميزة "إظهار عنوان المستند في شريط عنوان النافذة" باستخدام Aspose.Words for .NET؟
تتيح لك ميزة "إظهار عنوان المستند في شريط عنوان النافذة" مع Aspose.Words for .NET عرض عنوان المستند في شريط عنوان النافذة عند فتح مستند PDF الذي تم إنشاؤه. هذا يجعل من السهل التعرف على مستندات PDF وتمييزها في بيئة القراءة الخاصة بك.

#### س: كيف يمكنني استخدام هذه الميزة مع Aspose.Words for .NET؟
لاستخدام هذه الميزة مع Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتحميل المستند باستخدام ملف`Document` طريقة وتحديد مسار الملف للتحويل إلى PDF.

 قم بتكوين خيارات حفظ PDF عن طريق إنشاء مثيل لملف`PdfSaveOptions` الطبقة ووضع`DisplayDocTitle` ملكية ل`true`. يتيح ذلك عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF.

 استخدم ال`Save` طريقة لتحويل المستند إلى PDF مع تحديد خيارات التحويل.

#### س: هل تغير هذه الميزة محتوى المستند نفسه؟
لا ، لا تقوم هذه الميزة بتعديل محتوى المستند نفسه. إنه يؤثر فقط على عرض عنوان المستند في شريط عنوان النافذة عندما يتم فتحه كمستند PDF. محتوى الوثيقة يبقى دون تغيير.

#### س: هل من الممكن تخصيص عنوان المستند المعروض في شريط عنوان النافذة؟
 نعم ، يمكنك تخصيص عنوان المستند المعروض في شريط عنوان النافذة عن طريق تغيير`Document.Title` خاصية المستند قبل تحويله إلى PDF. يمكنك تعيين العنوان المطلوب باستخدام سلسلة. تأكد من تعيين العنوان قبل استدعاء`Save` طريقة التحويل إلى PDF.

#### س: ما هي تنسيقات الإخراج الأخرى التي يدعمها Aspose.Words لتحويل المستندات؟
يدعم Aspose.Words for .NET العديد من تنسيقات الإخراج لتحويل المستندات ، مثل PDF و XPS و HTML و EPUB و MOBI والصورة (JPEG و PNG و BMP و TIFF و GIF) وغيرها الكثير. لا يزال البعض الآخر. يمكنك اختيار تنسيق الإخراج المناسب وفقًا لاحتياجاتك الخاصة.