---
title: إزالة المعلومات الشخصية
linktitle: إزالة المعلومات الشخصية
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لإزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/remove-personal-information/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لإزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إزالة المعلومات الشخصية الحساسة من مستند ، مثل بيانات تعريف المؤلف.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد إزالة المعلومات الشخصية منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: حذف المعلومات الشخصية

 الآن سنعمل على تمكين إزالة المعلومات الشخصية عن طريق تعيين`RemovePersonalInformation` الملكية ل`true`. استخدم الكود التالي:

```csharp
doc.RemovePersonalInformation = true;
```

ينشط هذا الرمز حذف المعلومات الشخصية في المستند.

## الخطوة 4: حفظ المستند

أخيرًا ، سنحفظ المستند مع إزالة المعلومات الشخصية. استخدم الكود التالي:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

يحفظ هذا الرمز المستند مع إزالة المعلومات الشخصية إلى ملف جديد.

### مثال على شفرة المصدر لإزالة المعلومات الشخصية باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية إزالة المعلومات الشخصية من مستند باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إزالة المعلومات الحساسة من المستندات الخاصة بك.