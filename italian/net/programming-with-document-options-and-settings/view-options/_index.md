---
title: عرض الخيارات
linktitle: عرض الخيارات
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتكوين خيارات عرض المستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/view-options/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتكوين خيارات العرض باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تخصيص وضع العرض ومستوى التكبير / التصغير في المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد تكوين خيارات العرض له. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: تكوين خيارات العرض

الآن سنقوم بتكوين خيارات عرض المستند. استخدم الكود التالي لضبط وضع العرض ومستوى التكبير:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

يضبط هذا الرمز وضع العرض على "PageLayout" ومستوى التكبير / التصغير إلى 50٪.

### مثال على شفرة المصدر لخيارات العرض باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين خيارات عرض المستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تخصيص عرض المستندات الخاصة بك.