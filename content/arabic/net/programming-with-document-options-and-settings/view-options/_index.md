---
title: عرض الخيارات
linktitle: عرض الخيارات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتكوين خيارات عرض المستندات باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/view-options/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتكوين خيارات العرض باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تخصيص وضع العرض ومستوى التكبير/التصغير في المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد تكوين خيارات العرض له. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: تكوين خيارات العرض

الآن سنقوم بتكوين خيارات عرض المستندات. استخدم الكود التالي لضبط وضع العرض ومستوى التكبير/التصغير:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

يقوم هذا الرمز بتعيين وضع العرض على "PageLayout" ومستوى التكبير/التصغير إلى 50%.

### مثال على التعليمات البرمجية المصدر لخيارات العرض باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين خيارات عرض المستندات باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تخصيص عرض مستنداتك الخاصة.