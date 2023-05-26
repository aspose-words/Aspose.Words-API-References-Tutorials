---
title: تعيين إعداد الصفحة وتنسيق القسم
linktitle: تعيين إعداد الصفحة وتنسيق القسم
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإعداد تخطيط المستند وتنسيق القسم باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لإعداد تنسيق التخطيط والقسم باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تعيين اتجاه الصفحة والهوامش وحجم الورق.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إنشاء المستند

في هذه الخطوة ، سننشئ مستندًا جديدًا. استخدم الكود التالي لإنشاء المستند وتهيئة المنشئ:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل حيث تريد حفظ المستند.

## الخطوة 3: إعداد التخطيط وحفظ المستند

لنقم الآن بتهيئة تخطيط المستند. استخدم الكود التالي لتعيين الاتجاه والهوامش وحجم الورق:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

سيقوم هذا الرمز بتعيين اتجاه الصفحة إلى أفقي ، والهامش الأيسر على 50 ، وحجم الورق إلى 10x14.

### مثال على الكود المصدري لتعيين إعداد الصفحة وتنسيق القسم باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

تأكد من تحديد المسار الصحيح للدليل حيث تريد حفظ المستند بتنسيق`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين التخطيط وتنسيق القسم من المستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تخصيص تخطيط وتنسيق المستندات الخاصة بك.