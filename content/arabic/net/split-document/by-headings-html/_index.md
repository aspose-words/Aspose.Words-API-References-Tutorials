---
title: تقسيم مستند Word حسب العناوين HTML
linktitle: بواسطة العناوين أتش تي أم أل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لشرح الكود المصدري لـ C# لمستند الكلمات المقسمة عن طريق ميزة HTML الخاصة بـ Aspose.Words for .NET
type: docs
weight: 10
url: /ar/net/split-document/by-headings-html/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تقسيم مستند Word إلى أجزاء أصغر باستخدام ميزة By HTML Heading في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وإنشاء مستندات HTML منفصلة بناءً على العنوان.

## الخطوة 1: تحميل الوثيقة

للبدء، حدد الدليل للمستند الخاص بك وقم بتحميل المستند إلى كائن Document. إليك الطريقة:

```csharp
//المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## الخطوة 2: تقسيم المستند حسب العنوان بتنسيق HTML

سنقوم الآن بتعيين خيارات الحفظ لتقسيم المستند إلى أجزاء أصغر بناءً على العنوان بتنسيق HTML. إليك الطريقة:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// قم بتقسيم المستند إلى أجزاء أصغر، وفي هذه الحالة، قم بفصله حسب العنوان.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### مثال على التعليمات البرمجية المصدر لـ By Headings HTML باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة By HTML Heading في Aspose.Words لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// قم بتقسيم المستند إلى أجزاء أصغر، وفي هذه الحالة قم بالتقسيم حسب العنوان.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

باستخدام هذا الرمز، ستتمكن من تقسيم مستند Word إلى أجزاء أصغر باستخدام Aspose.Words for .NET، استنادًا إلى العناوين. يمكنك بعد ذلك إنشاء مستندات HTML منفصلة لكل جزء.

## خاتمة

 في هذا البرنامج التعليمي، تعلمنا كيفية تقسيم مستند Word إلى أجزاء أصغر باستخدام ميزة By HTML Heading في Aspose.Words for .NET. وذلك بتحديد`DocumentSplitCriteria` مثل`HeadingParagraph` في ال`HtmlSaveOptions`، تمكنا من إنشاء مستندات HTML منفصلة بناءً على العناوين الموجودة في المستند الأصلي.

يمكن أن يكون تقسيم المستند حسب العناوين مفيدًا لتنظيم المحتوى وإدارته، خاصة في المستندات الكبيرة التي تحتوي على أقسام متعددة. يوفر Aspose.Words for .NET حلاً موثوقًا وفعالاً للتعامل مع تقسيم المستندات وإنشاء المخرجات بتنسيقات مختلفة.

لا تتردد في استكشاف الميزات والخيارات الإضافية التي يوفرها Aspose.Words لـ .NET لتعزيز قدرات معالجة المستندات وتبسيط سير العمل لديك.

### الأسئلة الشائعة

#### كيف يمكنني تقسيم مستند Word إلى أجزاء أصغر بناءً على العناوين باستخدام Aspose.Words for .NET؟

 لتقسيم مستند Word استنادًا إلى العناوين، يمكنك استخدام ميزة By HTML Heading في Aspose.Words for .NET. اتبع كود المصدر المقدم وقم بتعيين`DocumentSplitCriteria` ل`HeadingParagraph` في ال`HtmlSaveOptions` هدف. سيؤدي هذا إلى تقسيم المستند إلى أجزاء أصغر في كل عنوان.

#### ما التنسيقات التي يمكنني تقسيم مستند Word إليها؟

 يوضح الكود المصدري المقدم تقسيم مستند Word إلى أجزاء أصغر بتنسيق HTML. ومع ذلك، يدعم Aspose.Words for .NET تنسيقات الإخراج المختلفة، بما في ذلك DOCX وPDF وEPUB والمزيد. يمكنك تعديل الكود وتحديد تنسيق الإخراج المطلوب في الملف`HtmlSaveOptions` الكائن وفقا لذلك.

#### هل يمكنني اختيار معايير مختلفة لتقسيم الوثيقة؟

نعم، يمكنك اختيار معايير مختلفة لتقسيم المستند بناءً على متطلباتك. يوفر Aspose.Words for .NET العديد من خيارات المعايير، مثل`HeadingParagraph`, `Page`, `Section` ، و اكثر. تعديل`DocumentSplitCriteria` الممتلكات في`HtmlSaveOptions` كائن لتحديد المعايير المناسبة للتقسيم.

#### كيف يمكنني تخصيص HTML الناتج للأجزاء المقسمة؟

 يسمح لك Aspose.Words for .NET بتخصيص إخراج HTML للأجزاء المقسمة عن طريق تحديد خيارات إضافية في`HtmlSaveOptions` هدف. يمكنك التحكم في جوانب مختلفة مثل أنماط CSS والصور والخطوط والمزيد. راجع وثائق Aspose.Words للحصول على مزيد من التفاصيل حول تخصيص مخرجات HTML.

#### هل يمكنني تقسيم المستند بناءً على معايير متعددة؟

 نعم، يمكنك تقسيم المستند بناءً على معايير متعددة من خلال دمج خيارات المعايير وفقًا لذلك. على سبيل المثال، يمكنك تقسيم المستند حسب كل من العنوان والصفحة عن طريق تعيين الإعداد`DocumentSplitCriteria`الملكية ل`HeadingParagraph | Page`. سيؤدي هذا إلى تقسيم المستند عند كل عنوان وكل صفحة، مما يؤدي إلى إنشاء أجزاء أصغر بناءً على كلا المعيارين.