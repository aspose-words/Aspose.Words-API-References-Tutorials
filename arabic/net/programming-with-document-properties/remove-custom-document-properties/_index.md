---
title: قم بإزالة خصائص المستند المخصصة
linktitle: قم بإزالة خصائص المستند المخصصة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لإزالة الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/remove-custom-document-properties/
---

في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # لإزالة الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إزالة خاصية مخصصة معينة من المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد إزالة الخصائص المخصصة منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: حذف الخصائص المخصصة

الآن دعنا نزيل خاصية مخصصة محددة من المستند. استخدم الكود التالي:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

يزيل هذا الرمز الخاصية المخصصة "تاريخ التخويل" من المستند. يمكنك استبدال "التاريخ المعتمد" باسم الخاصية المخصصة التي تريد إزالتها.

### مثال على شفرة المصدر لإزالة خصائص المستند المخصصة باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إزالة الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إزالة الخصائص المخصصة من المستندات الخاصة بك.