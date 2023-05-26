---
title: حسب نطاق الصفحة
linktitle: حسب نطاق الصفحة
second_title: Aspose.Words لمراجع .NET API
description: استخرج بسهولة حسب نطاق الصفحات من مستند Word باستخدام Aspose.Words for .NET دليل خطوة بخطوة.
type: docs
weight: 10
url: /tr/net/split-document/by-page-range/
---

## مقدمة
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لفهم واستخدام وظيفة "حسب نطاق الصفحات" في Aspose.Words for .NET. تتيح لك هذه الميزة استخراج جزء معين من مستند Word كبير باستخدام نطاق صفحات معين. سنزودك بكود مصدر كامل وتنسيقات إخراج Markdown لتسهيل فهمك واستخدامك لاحقًا.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. Aspose.Words for .NET مثبتة على جهاز التطوير الخاص بك.
2. ملف Word كبير تريد استخراج جزء معين منه.

الآن بعد أن غطينا المتطلبات ، يمكننا الانتقال إلى خطوات استخدام ميزة حسب نطاق الصفحات.

## الخطوة 1: تهيئة المستند وتحميله
بمجرد قيامك بإعداد بيئة التطوير الخاصة بك ، فإنك تحتاج إلى تهيئة وتحميل مستند Word الذي تريد استخراج جزء معين منه. هذا هو الكود الذي يجب استخدامه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

تأكد من استبدال "YOUR_DOCUMENTS_DIRECTORY" بالمسار الفعلي إلى دليل المستندات و "Name_of_large_document.docx" باسم ملف Word الكبير.

## الخطوة 2: استخراج جزء من المستند
 الآن بعد أن قمنا بتحميل المستند ، يمكننا استخراج الجزء المحدد باستخدام ملحق`ExtractPages` تعمل مع نطاق الصفحات المطلوب. هيريس كيفية القيام بذلك:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

في هذا المثال ، نستخرج الصفحات 3-6 من المستند الأصلي. يمكنك ضبط أرقام الصفحات وفقًا لاحتياجاتك.

## الخطوة 3: احفظ الجزء المستخرج
بمجرد استخراج الصفحات المطلوبة ، يمكننا حفظها في مستند Word جديد. إليك الطريقة:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

تأكد من استبدال "Document_Extraits.ParPlageDePages.docx" بالاسم المطلوب لملف الإخراج الخاص بك.

### مثال على شفرة المصدر لـ By Page Range باستخدام Aspose.Words for .NET

```csharp

            // المسار إلى دليل المستندات.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            // احصل على جزء من الوثيقة.
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## خاتمة
تهنئة ! لقد تعلمت كيفية استخدام "حسب نطاق الصفحات" من Aspose.Words for .NET. يمكنك الآن بسهولة استخراج أجزاء معينة من مستند Word كبير باستخدام نطاق صفحات معين. لا تتردد في تجربة المزيد مع ميزات Aspose القوية الأخرى. كلمات لتلبية احتياجاتك الخاصة.

