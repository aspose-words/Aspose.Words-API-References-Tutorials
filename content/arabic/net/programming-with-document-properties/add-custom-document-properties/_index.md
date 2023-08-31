---
title: إضافة خصائص الوثيقة المخصصة
linktitle: إضافة خصائص الوثيقة المخصصة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/add-custom-document-properties/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لإضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إضافة معلومات مخصصة إلى المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد إضافة خصائص مخصصة إليه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: إضافة خصائص مخصصة

الآن دعونا نضيف خصائص مخصصة إلى المستند. استخدم الكود التالي لإضافة الخصائص:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

يتحقق هذا الرمز أولاً مما إذا كانت الخاصية "المصرح بها" موجودة بالفعل في الخصائص المخصصة. إذا كان موجودا، تتم مقاطعة العملية. وبخلاف ذلك، تتم إضافة الخصائص المخصصة إلى المستند.

### مثال على التعليمات البرمجية المصدر لإضافة خصائص مستند مخصصة باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إضافة خصائصك المخصصة إلى مستنداتك.