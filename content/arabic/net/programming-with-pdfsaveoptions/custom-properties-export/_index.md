---
title: تصدير الخصائص المخصصة في وثيقة PDF
linktitle: تصدير الخصائص المخصصة في وثيقة PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تصدير الخصائص المخصصة عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/custom-properties-export/
---

في هذا البرنامج التعليمي، سنرشدك خلال خطوات تصدير الخصائص المخصصة للمستند في مستند PDF باستخدام Aspose.Words for .NET. يتيح لك تصدير الخصائص المخصصة تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: إنشاء مستند وإضافة خصائص مخصصة

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: إضافة خصائص مخصصة
 بعد ذلك، قم بإضافة الخصائص المخصصة المطلوبة. على سبيل المثال، لإضافة خاصية "شركة" بالقيمة "Aspose"، استخدم الخاصية`Add` طريقة مجموعة CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

يمكنك إضافة العديد من الخصائص المخصصة حسب الحاجة.

## الخطوة 3: ضبط خيارات تصدير PDF

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

### مثال على التعليمات البرمجية المصدر لتصدير الخصائص المخصصة باستخدام Aspose.Words لـ .NET

فيما يلي التعليمات البرمجية المصدر الكاملة لتصدير الخصائص المخصصة من مستند باستخدام Aspose.Words لـ .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

باتباع هذه الخطوات، يمكنك بسهولة تصدير الخصائص المخصصة للمستند عند التحويل إلى PDF باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تصدير الخصائص المخصصة من مستند إلى مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك بسهولة تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه عن طريق تصدير الخصائص المخصصة للمستند. استفد من ميزات Aspose.Words for .NET لتخصيص وإثراء مستندات PDF الخاصة بك عن طريق تصدير الخصائص المخصصة.

### أسئلة مكررة

#### س: ما هو تصدير الخصائص المخصصة إلى مستند PDF؟
ج: يسمح تصدير الخصائص المخصصة إلى مستند PDF بتضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه. الخصائص المخصصة هي بيانات تعريف خاصة بمستندك، مثل العلامات أو الكلمات الأساسية أو بيانات الاعتماد. من خلال تصدير هذه الخصائص المخصصة، يمكنك إتاحتها للمستخدمين عند عرض مستند PDF.

#### س: كيف يمكنني تصدير الخصائص المخصصة للمستند إلى مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتصدير الخصائص المخصصة للمستند إلى مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 إنشاء مثيل لـ`Document` فصل.

 قم بإضافة الخصائص المخصصة المطلوبة باستخدام`CustomDocumentProperties` مجموعة. على سبيل المثال، استخدم`Add` طريقة لإضافة خاصية "الشركة" بالقيمة "Aspose".

 إنشاء مثيل لـ`PdfSaveOptions` فئة وحدد كيفية تصدير الخصائص المخصصة باستخدام`CustomPropertiesExport` ملكية. ال`PdfCustomPropertiesExport.Standard` تقوم القيمة بتصدير الخصائص المخصصة وفقًا للإعدادات الافتراضية.

 استخدم ال`Save` طريقة`Document` فئة لتحويل المستند إلى PDF مع تحديد خيارات التحويل.

#### س: كيف يمكنني الوصول إلى الخصائص المخصصة لمستند PDF؟
ج: للوصول إلى الخصائص المخصصة لمستند PDF، يمكنك استخدام قارئ PDF متوافق يدعم عرض خصائص المستند. توفر معظم برامج قراءة PDF الشائعة، مثل Adobe Acrobat Reader، إمكانية الوصول إلى البيانات التعريفية وخصائص مستند PDF. يمكنك عادة العثور على هذه الخيارات ضمن قائمة "ملف" أو عن طريق النقر بزر الماوس الأيمن على المستند واختيار "خصائص".