---
title: تقسيم مستند Word حسب العناوين Html
linktitle: حسب العناوين Html
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # لمستند الكلمات المنقسمة عن طريق ميزة عنوان HTML في Aspose.Words for .NET
type: docs
weight: 10
url: /ar/net/split-document/by-headings-html/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تقسيم مستند Word إلى أجزاء أصغر باستخدام ميزة By HTML Heading في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وإنشاء مستندات HTML منفصلة استنادًا إلى العنوان.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستند الخاص بك وقم بتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## الخطوة 2: تقسيم المستند عن طريق العنوان بتنسيق HTML

سنقوم الآن بتعيين خيارات الحفظ لتقسيم المستند إلى أجزاء أصغر بناءً على العنوان بتنسيق HTML. إليك الطريقة:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// قسّم المستند إلى أجزاء أصغر ، في هذه الحالة افصله حسب العنوان.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### مثال على شفرة المصدر لـ By Headings HTML باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة By HTML Heading في Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// قسّم مستندًا إلى أجزاء أصغر ، في هذه الحالة ، قسم حسب العنوان.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

باستخدام هذا الرمز ، ستتمكن من تقسيم مستند Word إلى أجزاء أصغر باستخدام Aspose.Words for .NET ، بناءً على العناوين. يمكنك بعد ذلك إنشاء مستندات HTML منفصلة لكل جزء.

## خاتمة

 في هذا البرنامج التعليمي ، تعلمنا كيفية تقسيم مستند Word إلى أجزاء أصغر باستخدام ميزة By HTML Heading في Aspose.Words for .NET. بتحديد`DocumentSplitCriteria` مثل`HeadingParagraph` في ال`HtmlSaveOptions`، تمكنا من إنشاء مستندات HTML منفصلة استنادًا إلى العناوين الموجودة في المستند الأصلي.

يمكن أن يكون تقسيم المستند حسب العناوين مفيدًا لتنظيم المحتوى وإدارته ، خاصة في المستندات الكبيرة ذات الأقسام المتعددة. يوفر Aspose.Words for .NET حلاً موثوقًا وفعالًا لمعالجة تقسيم المستندات وتوليد المخرجات بتنسيقات مختلفة.

لا تتردد في استكشاف الميزات والخيارات الإضافية التي توفرها Aspose.Words for .NET لزيادة تحسين إمكانات معالجة المستندات وتسهيل سير عملك.

### أسئلة وأجوبة

#### كيف يمكنني تقسيم مستند Word إلى أجزاء أصغر بناءً على العناوين باستخدام Aspose.Words for .NET؟

 لتقسيم مستند Word استنادًا إلى العناوين ، يمكنك استخدام ميزة By HTML Heading في Aspose.Words for .NET. اتبع كود المصدر المقدم وقم بتعيين ملف`DocumentSplitCriteria` ل`HeadingParagraph` في ال`HtmlSaveOptions` هدف. سيؤدي هذا إلى تقسيم المستند إلى أجزاء أصغر في كل عنوان.

#### ما هي التنسيقات التي يمكنني تقسيم مستند Word إليها؟

يوضح كود المصدر المقدم تقسيم مستند Word إلى أجزاء أصغر بتنسيق HTML. ومع ذلك ، يدعم Aspose.Words for .NET تنسيقات إخراج متنوعة ، بما في ذلك DOCX و PDF و EPUB والمزيد. يمكنك تعديل الكود وتحديد تنسيق الإخراج المطلوب في ملف`HtmlSaveOptions` بناء على ذلك.

#### هل يمكنني اختيار معايير مختلفة لتقسيم الوثيقة؟

 نعم ، يمكنك اختيار معايير مختلفة لتقسيم المستند بناءً على متطلباتك. يوفر Aspose.Words for .NET العديد من خيارات المعايير ، مثل`HeadingParagraph`, `Page`, `Section` ، و اكثر. تعديل`DocumentSplitCriteria` الممتلكات في`HtmlSaveOptions` كائن لتحديد المعايير المناسبة للتقسيم.

#### كيف يمكنني تخصيص ناتج HTML للأجزاء المنقسمة؟

 يتيح لك Aspose.Words for .NET تخصيص مخرجات HTML للأجزاء المنقسمة من خلال تحديد خيارات إضافية في ملف`HtmlSaveOptions` هدف. يمكنك التحكم في جوانب مختلفة مثل أنماط CSS والصور والخطوط والمزيد. راجع وثائق Aspose.Words لمزيد من التفاصيل حول تخصيص مخرجات HTML.

#### هل يمكنني تقسيم المستند بناءً على معايير متعددة؟

 نعم ، يمكنك تقسيم المستند بناءً على معايير متعددة من خلال دمج خيارات المعايير وفقًا لذلك. على سبيل المثال ، يمكنك تقسيم المستند حسب العنوان والصفحة عن طريق تعيين ملف`DocumentSplitCriteria` ملكية ل`HeadingParagraph | Page`. سيؤدي هذا إلى تقسيم المستند في كل عنوان وكل صفحة ، مما يؤدي إلى إنشاء أجزاء أصغر بناءً على كلا المعيارين.