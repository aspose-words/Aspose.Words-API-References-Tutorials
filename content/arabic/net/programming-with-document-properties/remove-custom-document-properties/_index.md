---
title: إزالة خصائص المستند المخصصة
linktitle: إزالة خصائص المستند المخصصة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإزالة الخصائص المخصصة من مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/remove-custom-document-properties/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لإزالة الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET. تسمح لك هذه الميزة بإزالة خاصية مخصصة معينة من المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد إزالة الخصائص المخصصة منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: حذف الخصائص المخصصة

لنقم الآن بإزالة خاصية مخصصة محددة من المستند. استخدم الكود التالي:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

يقوم هذا الرمز بإزالة الخاصية المخصصة "التاريخ المعتمد" من المستند. يمكنك استبدال "التاريخ المعتمد" باسم الخاصية المخصصة التي تريد إزالتها.

### مثال للتعليمة البرمجية المصدر لإزالة خصائص المستند المخصصة باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إزالة الخصائص المخصصة من مستند باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إزالة الخصائص المخصصة من مستنداتك الخاصة.