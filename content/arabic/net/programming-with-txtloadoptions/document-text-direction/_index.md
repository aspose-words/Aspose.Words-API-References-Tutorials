---
title: اتجاه نص الوثيقة
linktitle: اتجاه نص الوثيقة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد اتجاه النص في مستنداتك باستخدام Aspose.Words for .NET. تحسين العرض للغات التي تكتب من اليمين إلى اليسار.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/document-text-direction/
---

في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم لميزة "اتجاه نص المستند" مع Aspose.Words for .NET. تتيح لك هذه الميزة تحديد اتجاه النص في المستند، وهو أمر مفيد بشكل خاص للغات المكتوبة من اليمين إلى اليسار، مثل العبرية أو العربية.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: تكوين خيارات التحميل

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 في هذه الخطوة، نقوم بتكوين خيارات تحميل المستندات. نحن نخلق جديدا`TxtLoadOptions` الكائن وتعيين`DocumentDirection`الملكية ل`DocumentDirection.Auto`. تخبر هذه القيمة Aspose.Words بتحديد اتجاه النص تلقائيًا بناءً على محتوى المستند.

## الخطوة 3: تحميل الوثيقة

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى الملف النصي للتحميل. نستخدم أيضًا خيارات التحميل المحددة.

## الخطوة 4: معالجة الفقرة وعرض اتجاه النص

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 في هذه الخطوة، نقوم بالوصول إلى الفقرة الأولى من المستند باستخدام الملف`FirstSection` و`Body` ملكيات. بعد ذلك، نقوم بالوصول إلى`ParagraphFormat.Bidi` خاصية الحصول على اتجاه النص للفقرة. ثم نعرض هذه القيمة في وحدة التحكم.

## الخطوة 5: احفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند الناتج بتنسيق .docx باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج.

يمكنك الآن تشغيل الكود المصدري لتحميل المستند النصي وتحديد اتجاه النص. سيتم حفظ المستند الناتج في الدليل المحدد بالاسم "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### نموذج التعليمات البرمجية المصدر لوظيفة توجيه نص المستند باستخدام Aspose.Words لـ .NET.


```csharp

            
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة اتجاه نص المستند في Aspose.Words لـ .NET. تعلمنا كيفية تحديد اتجاه النص في المستند، خاصة بالنسبة للغات التي تكتب من اليمين إلى اليسار، مثل العبرية أو العربية.

تعد هذه الميزة ضرورية لضمان عرض النص بشكل صحيح في المستندات متعددة اللغات. باستخدام خيارات التحميل المناسبة، يمكن لـ Aspose.Words اكتشاف اتجاه النص تلقائيًا وتطبيقه على المستند.

باستخدام Aspose.Words، يمكنك بسهولة التعامل مع اتجاه النص في مستنداتك، مما يوفر تجربة قراءة سلسة وبديهية للمستخدمين.

من المهم ملاحظة أن هذه الميزة مفيدة بشكل خاص عند معالجة الكلمات باللغات التي تتطلب اتجاهًا محددًا للنص. يجعل Aspose.Words هذه المهمة سهلة من خلال توفير أدوات قوية لإدارة اتجاه النص في مستنداتك.

تذكر استخدام خيارات التحميل المناسبة، مثل تعيين اتجاه النص التلقائي، للحصول على النتائج التي تريدها في مستنداتك.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. ومن خلال استكشاف المزيد من الوثائق والأمثلة المقدمة من Aspose.Words، ستتمكن من استغلال إمكانيات هذه المكتبة القوية بشكل كامل.

لذا، لا تتردد في دمج اتجاه نص المستند في مشاريع Aspose.Words الخاصة بـ .NET والاستفادة من فوائدها لإنشاء مستندات متعددة اللغات جذابة وعالية الجودة.