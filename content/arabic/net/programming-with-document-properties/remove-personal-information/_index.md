---
title: إزالة المعلومات الشخصية
linktitle: إزالة المعلومات الشخصية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/remove-personal-information/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لإزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إزالة المعلومات الشخصية الحساسة من المستند، مثل بيانات تعريف المؤلف.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد إزالة المعلومات الشخصية منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: حذف المعلومات الشخصية

 الآن سنقوم بتمكين إزالة المعلومات الشخصية عن طريق تعيين`RemovePersonalInformation`الملكية ل`true`. استخدم الكود التالي:

```csharp
doc.RemovePersonalInformation = true;
```

يقوم هذا الرمز بتنشيط حذف المعلومات الشخصية في المستند.

## الخطوة 4: حفظ الوثيقة

وأخيرًا، سنقوم بحفظ المستند مع إزالة المعلومات الشخصية. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

يحفظ هذا الرمز المستند مع إزالة المعلومات الشخصية في ملف جديد.

### مثال على التعليمات البرمجية المصدر لإزالة المعلومات الشخصية باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إزالة المعلومات الحساسة من مستنداتك الخاصة.