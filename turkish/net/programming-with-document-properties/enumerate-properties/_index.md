---
title: تعداد الخصائص
linktitle: تعداد الخصائص
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتعداد خصائص المستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/enumerate-properties/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتعداد خصائص المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى الخصائص المضمنة والمخصصة للمستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد سرد خصائصه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة الثالثة: تعداد الخصائص

الآن دعنا ندرج خصائص المستند ، الخصائص المضمنة والمخصصة. استخدم الكود التالي:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

يعرض هذا الرمز اسم المستند ثم يسرد الخصائص المضمنة والمخصصة التي تعرض اسمها وقيمتها.

### مثال على شفرة المصدر لـ Enumerate Properties باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تعداد خصائص المستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك الوصول بسهولة إلى خصائص المستندات الخاصة بك وعرضها.

