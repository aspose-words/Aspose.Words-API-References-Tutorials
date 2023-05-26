---
title: أضف خصائص المستند المخصصة
linktitle: أضف خصائص المستند المخصصة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/add-custom-document-properties/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لإضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إضافة معلومات مخصصة إلى المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد إضافة خصائص مخصصة إليه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: إضافة خصائص مخصصة

الآن دعنا نضيف خصائص مخصصة إلى المستند. استخدم الكود التالي لإضافة الخصائص:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

يتحقق هذا الرمز أولاً مما إذا كانت الخاصية "معتمد" موجودة بالفعل في الخصائص المخصصة. إذا كان موجودًا ، فستتوقف العملية. وبخلاف ذلك ، تتم إضافة الخصائص المخصصة إلى المستند.

### مثال على شفرة المصدر لإضافة خصائص وثيقة مخصصة باستخدام Aspose.Words for .NET

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

لقد تعلمت الآن كيفية إضافة خصائص مخصصة إلى مستند باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إضافة خصائصك المخصصة إلى مستنداتك.