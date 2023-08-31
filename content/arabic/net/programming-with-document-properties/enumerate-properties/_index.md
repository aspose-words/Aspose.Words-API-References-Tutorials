---
title: تعداد الخصائص
linktitle: تعداد الخصائص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتعداد خصائص المستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/enumerate-properties/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لتعداد خصائص المستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى الخصائص المضمنة والمخصصة للمستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد إدراج خصائصه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: تعداد الخصائص

الآن دعونا ندرج خصائص المستند، سواء الخصائص المضمنة أو المخصصة. استخدم الكود التالي:

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

### مثال على التعليمات البرمجية المصدر لتعداد الخصائص باستخدام Aspose.Words لـ .NET

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

لقد تعلمت الآن كيفية تعداد خصائص المستند باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك الوصول بسهولة إلى خصائص المستندات الخاصة بك وعرضها.

