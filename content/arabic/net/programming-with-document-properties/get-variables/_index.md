---
title: الحصول على المتغيرات
linktitle: الحصول على المتغيرات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لاسترداد متغيرات المستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/get-variables/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لاسترداد المتغيرات من مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى المتغيرات المحددة في المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد استرجاع المتغيرات منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: استرجاع المتغيرات

الآن سوف نقوم باسترداد المتغيرات المحددة في الوثيقة. استخدم الكود التالي:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

يتكرر هذا الرمز على كل زوج من المفاتيح والقيمة في متغيرات المستند ويسترد اسم وقيمة كل متغير. يتم بعد ذلك ربط المتغيرات لعرض المعلومات الخاصة بكل متغير.

### مثال على التعليمات البرمجية المصدر للحصول على المتغيرات باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية استرداد المتغيرات من مستند باستخدام Aspose.Words لـ .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة الوصول إلى المتغيرات وعرضها من مستنداتك الخاصة.