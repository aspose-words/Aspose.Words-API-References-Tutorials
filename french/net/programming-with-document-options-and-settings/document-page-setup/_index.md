---
title: وثيقة إعداد الصفحة
linktitle: وثيقة إعداد الصفحة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإعداد تخطيط مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/document-page-setup/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتكوين تخطيط المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة ضبط وضع التخطيط وعدد الأحرف في كل سطر وعدد الأسطر في كل صفحة.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد تهيئته. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: إعداد التخطيط

لنقم الآن بتهيئة تخطيط المستند. استخدم الكود التالي لضبط وضع التخطيط ، وعدد الأحرف في كل سطر ، وعدد الأسطر في كل صفحة:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

يقوم هذا الرمز بتعيين وضع التخطيط على "الشبكة" ثم يحدد عدد الأحرف في كل سطر وعدد الأسطر في كل صفحة.

### مثال على الكود المصدري لإعداد صفحة المستند باستخدام Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// اضبط وضع التخطيط لقسم يسمح بتعريف سلوك شبكة الوثيقة.
	// لاحظ أن علامة التبويب Document Grid تصبح مرئية في مربع حوار إعداد الصفحة في MS Word
	// إذا تم تعريف أي لغة آسيوية على أنها لغة تحرير.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين تخطيط المستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تخصيص تخطيط المستندات الخاصة بك.