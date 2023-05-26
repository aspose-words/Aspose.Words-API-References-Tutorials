---
title: استبدال النص في التذييل
linktitle: استبدال النص في التذييل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استبدال النص في تذييل مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-in-footer/
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
