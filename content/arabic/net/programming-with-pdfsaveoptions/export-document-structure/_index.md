---
title: تصدير بنية مستند Word إلى مستند PDF
linktitle: تصدير بنية مستند Word إلى مستند PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/export-document-structure/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة تصدير بنية مستند Word إلى مستند PDF مع Aspose.Words for .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستكون قادرًا على فهم كيفية تصدير بنية المستند وإنشاء ملف PDF مع ظهور بنية المستند.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء، تحتاج إلى تحديد المسار إلى الدليل الذي توجد به مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة

بعد ذلك، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال، نفترض أن المستند يسمى "Paragraphs.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## الخطوة 3: تكوين خيارات الحفظ بتنسيق PDF

 لتصدير بنية المستند وجعل البنية مرئية في جزء التنقل "المحتوى" في Adobe Acrobat Pro أثناء تحرير ملف PDF، نحتاج إلى تكوين`PdfSaveOptions` كائن مع`ExportDocumentStructure` خاصية تعيين ل`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## الخطوة 4: احفظ المستند كملف PDF مع بنية المستند

أخيرًا، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تصدير بنية مستند وإنشاء ملف PDF مع ظهور بنية المستند باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لتصدير بنية المستند باستخدام Aspose.Words لـ .NET


```csharp

            // المسار إلى دليل المستندات.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // سيتم زيادة حجم الملف وستكون البنية مرئية في جزء التنقل "المحتوى".
            // لبرنامج Adobe Acrobat Pro، أثناء تحرير ملف .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك بسهولة إنشاء ملف PDF مع ظهور بنية المستند، مما يسهل التنقل والبحث خلال المستند. استخدم ميزات Aspose.Words for .NET لتصدير بنية مستندات Word الخاصة بك وإنشاء ملفات PDF جيدة التنظيم.

### أسئلة مكررة

#### س: ما هو تصدير بنية مستند Word إلى مستند PDF؟
ج: يؤدي تصدير بنية مستند Word إلى مستند PDF إلى إنشاء ملف PDF ببنية مستند مرئية. تتضمن بنية المستند عادةً أشياء مثل العناوين والأقسام والفقرات والعناصر المنظمة الأخرى للمستند. يمكن أن تكون هذه البنية مفيدة للتنقل والبحث في مستند PDF.

#### س: كيف يمكنني تصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتصدير بنية مستند Word إلى مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 إنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 إنشاء مثيل لـ`PdfSaveOptions`فئة وتعيين`ExportDocumentStructure` الملكية ل`true`. سيؤدي هذا إلى تصدير بنية المستند وجعلها مرئية في جزء التنقل "المحتوى" في Adobe Acrobat Pro عند تحرير ملف PDF.

 استخدم ال`Save` طريقة`Document`فئة لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: كيف يمكنني عرض بنية مستند PDF باستخدام Adobe Acrobat Pro؟
ج: لعرض بنية مستند PDF باستخدام Adobe Acrobat Pro، اتبع الخطوات التالية:

افتح مستند PDF في Adobe Acrobat Pro.

في شريط التنقل الأيسر، انقر فوق أيقونة "المحتوى" لعرض جزء التنقل "المحتوى".

في جزء التنقل "المحتوى"، سترى بنية المستند مع العناوين والأقسام والعناصر المنظمة الأخرى.