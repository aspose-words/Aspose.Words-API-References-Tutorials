---
title: ضبط إعداد الصفحة وتنسيق القسم
linktitle: ضبط إعداد الصفحة وتنسيق القسم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد تخطيط المستند وتنسيق القسم باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لإعداد التخطيط وتنسيق الأقسام باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة ضبط اتجاه الصفحة والهوامش وحجم الورق.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إنشاء الوثيقة

في هذه الخطوة، سنقوم بإنشاء مستند جديد. استخدم الكود التالي لإنشاء المستند وتهيئة المُنشئ:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي تريد حفظ المستند فيه.

## الخطوة 3: إعداد التخطيط وحفظ المستند

الآن دعونا نقوم بتكوين تخطيط المستند. استخدم الكود التالي لتعيين الاتجاه والهوامش وحجم الورق:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

سيقوم هذا الرمز بتعيين اتجاه الصفحة إلى أفقي، والهامش الأيسر إلى 50، وحجم الورق إلى 10x14.

### مثال على التعليمات البرمجية المصدر لإعداد الصفحة وتنسيق القسم باستخدام Aspose.Words لـ .NET

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

تأكد من تحديد المسار الصحيح للدليل الذي تريد حفظ المستند فيه`dataDir` عامل.

لقد تعلمت الآن كيفية تكوين التخطيط وتنسيق الأقسام للمستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تخصيص تخطيط وتنسيق مستنداتك الخاصة.