---
title: إعداد صفحة المستند
linktitle: إعداد صفحة المستند
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد تخطيط مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/document-page-setup/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لتكوين تخطيط المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة ضبط وضع التخطيط وعدد الأحرف في كل سطر وعدد الأسطر في كل صفحة.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد تكوينه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: إعداد التخطيط

الآن دعونا نقوم بتكوين تخطيط المستند. استخدم الكود التالي لتعيين وضع التخطيط، وعدد الأحرف في كل سطر، وعدد الأسطر في كل صفحة:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

يقوم هذا الرمز بتعيين وضع التخطيط على "الشبكة" ثم يحدد عدد الأحرف في كل سطر وعدد الأسطر في كل صفحة.

### مثال للتعليمة البرمجية المصدر لإعداد صفحة المستند باستخدام Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// قم بتعيين وضع التخطيط لقسم يسمح بتحديد سلوك شبكة المستند.
	// لاحظ أن علامة التبويب "شبكة المستند" تصبح مرئية في مربع حوار "إعداد الصفحة" في برنامج MS Word.
	// إذا تم تعريف أي لغة آسيوية على أنها لغة تحرير.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين تخطيط المستند باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تخصيص تخطيط مستنداتك الخاصة.