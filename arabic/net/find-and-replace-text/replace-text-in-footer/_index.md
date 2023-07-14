---
title: استبدال النص في التذييل
linktitle: استبدال النص في التذييل
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استبدال النص في تذييل مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-text-in-footer/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة استبدال النص في التذييل في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة البحث عن نص معين واستبداله في تذييلات مستندات Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: قم بتحميل المستند

قبل أن نبدأ في استخدام استبدال النص في التذييل ، نحتاج إلى تحميل المستند إلى Aspose.Words for .NET. يمكن القيام بذلك باستخدام ملف`Document` فئة وتحديد مسار ملف المستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## الخطوة 2: الوصول إلى التذييل

 بمجرد تحميل المستند ، نحتاج إلى الوصول إلى التذييل لإجراء استبدال النص. في مثالنا ، نستخدم الامتداد`HeadersFooters` خاصية القسم الأول من المستند للحصول على مجموعة الرؤوس / التذييلات. بعد ذلك ، نختار التذييل الرئيسي باستخدام`HeaderFooterType.FooterPrimary` فِهرِس:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## الخطوة 3: تكوين خيارات البحث والاستبدال

 سنقوم الآن بتكوين خيارات البحث والاستبدال باستخدام ملف`FindReplaceOptions` هدف. في مثالنا ، حددنا`MatchCase` ل`false` لتجاهل الحالة عند البحث ، و`FindWholeWordsOnly` ل`false` للسماح بالبحث عن أجزاء من الكلمات واستبدالها:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## الخطوة 4: استبدال النص في التذييل

 نحن نستخدم ال`Range.Replace` طريقة لإجراء استبدال النص في التذييل. في مثالنا ، نستبدل العبارة "(C) 2006 Aspose Pty Ltd." بواسطة "حقوق الطبع والنشر (C) 2020 لشركة Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## الخطوة 5: احفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### مثال على شفرة المصدر لاستبدال النص في التذييل باستخدام Aspose.Words لـ .NET

إليك نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام استبدال نص التذييل بـ Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة استبدال النص في التذييل في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا خطوة بخطوة لتحميل مستند ، والوصول إلى التذييل ، وتكوين خيارات البحث والاستبدال ، وإجراء استبدال النص ، وحفظ المستند المحرر.

### التعليمات

#### س: ما هي ميزة "استبدال النص في التذييل" في Aspose.Words لـ .NET؟

ج: تسمح لك ميزة "استبدال النص في التذييل" في Aspose.Words for .NET بالعثور على نص معين واستبداله في تذييلات مستندات Word. يمكّنك من تعديل محتوى التذييل عن طريق استبدال عبارة أو كلمة أو نمط معين بالنص المطلوب.

#### س: كيف يمكنني تحميل مستند Word باستخدام Aspose.Words for .NET؟

ج: لتحميل مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام`Document` class وحدد مسار ملف المستند. فيما يلي مثال على رمز C # لتحميل مستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

#### س: كيف يمكنني الوصول إلى تذييل مستند في Aspose.Words for .NET؟

 ج: بمجرد تحميل المستند ، يمكنك الوصول إلى التذييل لإجراء استبدال النص. في Aspose.Words for .NET ، يمكنك استخدام ملحق`HeadersFooters` خاصية القسم الأول من المستند للحصول على مجموعة الرؤوس / التذييلات. بعد ذلك ، يمكنك تحديد التذييل الرئيسي باستخدام ملف`HeaderFooterType.FooterPrimary` فِهرِس:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

#### س: كيف يمكنني تكوين خيارات البحث والاستبدال لاستبدال النص في التذييل باستخدام Aspose.Words for .NET؟

 ج: لتكوين خيارات البحث والاستبدال لاستبدال النص في التذييل باستخدام Aspose.Words for .NET ، يمكنك إنشاء ملف`FindReplaceOptions` الكائن وتعيين الخصائص المطلوبة. على سبيل المثال ، يمكنك ضبط`MatchCase` ل`false` لتجاهل الحالة عند البحث و`FindWholeWordsOnly` ل`false` للسماح بالبحث عن أجزاء من الكلمات واستبدالها:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

#### س: كيف يمكنني إجراء استبدال النص في التذييل باستخدام Aspose.Words for .NET؟

ج: لإجراء استبدال النص في التذييل باستخدام Aspose.Words لـ .NET ، يمكنك استخدام`Range.Replace` الطريقة في نطاق التذييل. تسمح لك هذه الطريقة بتحديد النص الذي تريد البحث عنه والنص البديل. هذا مثال:

```csharp
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

#### س: هل يمكنني إجراء استبدال النص في تذييلات متعددة من مستند باستخدام Aspose.Words for .NET؟

 ج: نعم ، يمكنك إجراء استبدال النص في تذييلات متعددة من المستند باستخدام Aspose.Words for .NET. يمكنك التكرار على امتداد`HeaderFooterCollection` وتطبيق استبدال النص على كل تذييل على حدة. يسمح لك هذا باستبدال نص معين في جميع التذييلات الموجودة في المستند.

#### س: ما الذي يوضحه مثال كود المصدر لميزة "استبدال النص في التذييل" في Aspose.Words for .NET؟

ج: يوضح مثال كود المصدر استخدام ميزة "استبدال النص في التذييل" في Aspose.Words for .NET. يوضح كيفية تحميل مستند ، والوصول إلى التذييل ، وتكوين خيارات البحث والاستبدال ، وإجراء استبدال النص في التذييل ، وحفظ المستند المعدل.

#### س: هل هناك أي قيود أو اعتبارات عند استبدال النص في التذييلات باستخدام Aspose.Words for .NET؟

ج: عند استبدال نص في التذييلات باستخدام Aspose.Words لـ .NET ، من المهم مراعاة تنسيق وتخطيط التذييل. إذا كان النص البديل يختلف اختلافًا كبيرًا في الطول أو التنسيق ، فقد يؤثر على مظهر التذييل. تأكد من أن النص البديل يتماشى مع التصميم العام وهيكل التذييل للحفاظ على تخطيط متسق.

#### س: هل يمكنني استخدام التعبيرات العادية لاستبدال النص في التذييلات باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك استخدام التعبيرات العادية لاستبدال النص في التذييلات باستخدام Aspose.Words for .NET. من خلال إنشاء نمط تعبير عادي ، يمكنك إجراء مطابقة أكثر تقدمًا ومرونة لاستبدال النص في التذييل. يتيح لك ذلك التعامل مع أنماط البحث المعقدة وإجراء عمليات الاستبدال الديناميكية بناءً على المجموعات أو الأنماط التي تم التقاطها.

#### س: هل يمكنني استبدال النص في أجزاء أخرى من المستند إلى جانب التذييلات باستخدام Aspose.Words for .NET؟

 ج: نعم ، يمكنك استبدال النص في أجزاء أخرى من المستند إلى جانب التذييلات باستخدام Aspose.Words for .NET. ال`Range.Replace` يمكن استخدام الطريقة لاستبدال النص في أقسام المستند المختلفة أو الرؤوس أو النص الأساسي أو أي موقع آخر مرغوب فيه. ما عليك سوى استهداف النطاق أو المنطقة المناسبة داخل المستند وتنفيذ عملية استبدال النص وفقًا لذلك.