---
title: تصدير الخصائص المخصصة في مستند PDF
linktitle: تصدير الخصائص المخصصة في مستند PDF
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تصدير الخصائص المخصصة عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/custom-properties-export/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات تصدير الخصائص المخصصة للمستند في مستند PDF باستخدام Aspose.Words for .NET. يتيح لك تصدير الخصائص المخصصة تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: إنشاء مستند وإضافة خصائص مخصصة

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: إضافة خصائص مخصصة
 بعد ذلك ، أضف الخصائص المخصصة المطلوبة. على سبيل المثال ، لإضافة خاصية "شركة" بالقيمة "Aspose" ، استخدم`Add` طريقة مجموعة CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

يمكنك إضافة العديد من الخصائص المخصصة حسب الحاجة.

## الخطوة 3: قم بتعيين خيارات تصدير PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد كيفية تصدير الخصائص المخصصة:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

يتحكم هذا الخيار في تصدير الخصائص المخصصة عند التحويل إلى PDF.

## الخطوة 4: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لتصدير الخصائص المخصصة باستخدام Aspose.Words for .NET

إليك التعليمات البرمجية المصدر الكاملة لتصدير الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك بسهولة تصدير الخصائص المخصصة للمستند عند التحويل إلى PDF باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تصدير الخصائص المخصصة من مستند إلى مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك بسهولة تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه عن طريق تصدير خصائص المستند المخصصة. استفد من ميزات Aspose.Words for .NET لتخصيص وإثراء مستندات PDF الخاصة بك عن طريق تصدير خصائص مخصصة.

### أسئلة مكررة

#### س: ما هو تصدير الخصائص المخصصة إلى مستند PDF؟
ج: يتيح تصدير الخصائص المخصصة إلى مستند PDF تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه. الخصائص المخصصة هي بيانات تعريف خاصة بمستندك ، مثل العلامات أو الكلمات الأساسية أو بيانات الاعتماد. بتصدير هذه الخصائص المخصصة ، يمكنك إتاحتها للمستخدمين عند عرض وثيقة PDF.

#### س: كيف يمكنني تصدير الخصائص المخصصة لمستند ما إلى مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتصدير الخصائص المخصصة لمستند ما إلى مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بإنشاء مثيل لـ`Document` فصل.

 أضف الخصائص المخصصة المطلوبة باستخدام ملف`CustomDocumentProperties` مجموعة. على سبيل المثال ، استخدم ملف`Add` طريقة لإضافة خاصية "شركة" بقيمة "Aspose".

 قم بإنشاء مثيل لـ`PdfSaveOptions` class وتحديد كيفية تصدير الخصائص المخصصة باستخدام امتداد`CustomPropertiesExport` ملكية. ال`PdfCustomPropertiesExport.Standard` تصدر value الخصائص المخصصة وفقًا للإعدادات الافتراضية.

 استخدم ال`Save` طريقة`Document` class لتحويل المستند إلى PDF مع تحديد خيارات التحويل.

#### س: كيف يمكنني الوصول إلى الخصائص المخصصة لمستند PDF؟
ج: للوصول إلى الخصائص المخصصة لمستند PDF ، يمكنك استخدام قارئ PDF متوافق يدعم عرض خصائص المستند. توفر معظم برامج قراءة PDF الشائعة ، مثل Adobe Acrobat Reader ، إمكانية الوصول إلى البيانات الأولية وخصائص مستند PDF. يمكنك عادةً العثور على هذه الخيارات ضمن قائمة "ملف" أو بالنقر بزر الماوس الأيمن فوق المستند وتحديد "خصائص".