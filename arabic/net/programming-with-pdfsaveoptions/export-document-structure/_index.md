---
title: تصدير بنية مستند Word إلى مستند PDF
linktitle: تصدير بنية مستند Word إلى مستند PDF
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/export-document-structure/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة تصدير بنية مستند Word إلى مستند PDF مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، سوف تكون قادرًا على فهم كيفية تصدير بنية المستند وإنشاء ملف PDF بهيكل المستند المرئي.

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
            // من Adobe Acrobat Pro ، أثناء تحرير ملف .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية تصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك بسهولة إنشاء ملف PDF مع إظهار هيكل المستند الخاص بك ، مما يسهل التنقل والبحث في المستند. استخدم ميزات Aspose.Words for .NET لتصدير بنية مستندات Word وإنشاء ملفات PDF جيدة التنظيم.

### أسئلة مكررة

#### س: ما المقصود بتصدير بنية مستند Word إلى مستند PDF؟
ج: يؤدي تصدير بنية مستند Word إلى مستند PDF إلى إنشاء ملف PDF بهيكل مستند مرئي. تتضمن بنية المستند عادةً أشياء مثل العناوين والأقسام والفقرات والعناصر المنظمة الأخرى في المستند. يمكن أن تكون هذه البنية مفيدة للتنقل والبحث في مستند PDF.

#### س: كيف يمكنني تصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بإنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 قم بإنشاء مثيل لـ`PdfSaveOptions` فئة وضبط`ExportDocumentStructure` الملكية ل`true`. سيؤدي هذا إلى تصدير هيكل المستند وجعله مرئيًا في جزء التنقل "المحتوى" في Adobe Acrobat Pro عند تحرير ملف PDF.

 استخدم ال`Save` طريقة`Document`class لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: كيف يمكنني عرض بنية مستند PDF باستخدام Adobe Acrobat Pro؟
ج: لعرض بنية مستند PDF باستخدام Adobe Acrobat Pro ، اتبع الخطوات التالية:

افتح مستند PDF في Adobe Acrobat Pro.

في شريط التنقل الأيمن ، انقر فوق رمز "المحتوى" لعرض جزء التنقل "المحتوى".

في جزء التنقل "المحتوى" ، سترى بنية المستند مع العناوين والأقسام والعناصر المنظمة الأخرى.