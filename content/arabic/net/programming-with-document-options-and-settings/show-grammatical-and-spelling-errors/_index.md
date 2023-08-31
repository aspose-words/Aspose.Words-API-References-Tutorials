---
title: إظهار الأخطاء النحوية والإملائية
linktitle: إظهار الأخطاء النحوية والإملائية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتمكين عرض الأخطاء النحوية والإملائية في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتمكين عرض الأخطاء النحوية والإملائية باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة عرض الأخطاء النحوية والإملائية في المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد عرض الأخطاء النحوية والإملائية له. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: تمكين عرض الأخطاء

سنقوم الآن بتمكين عرض الأخطاء النحوية والإملائية في المستند. استخدم الكود التالي لتمكين عرض الأخطاء:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

يتيح هذا الرمز عرض الأخطاء النحوية (`ShowGrammaticalErrors`) والأخطاء الإملائية (`ShowSpellingErrors`) في الوثيقة.

### مثال على التعليمات البرمجية المصدر لإظهار الأخطاء النحوية والإملائية باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تمكين عرض الأخطاء النحوية والإملائية في مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تمكين هذه الميزة في مستنداتك الخاصة.