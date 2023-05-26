---
title: احصل على المتغيرات
linktitle: احصل على المتغيرات
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لاسترداد متغيرات المستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/get-variables/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لاسترداد المتغيرات من مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى المتغيرات المحددة في المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد استرداد المتغيرات منه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: استرجاع المتغيرات

الآن سنقوم باسترداد المتغيرات المحددة في المستند. استخدم الكود التالي:

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

يتكرر هذا الرمز فوق كل زوج من القيم الرئيسية في متغيرات المستند ويسترجع اسم وقيمة كل متغير. ثم يتم تسلسل المتغيرات لعرض المعلومات الخاصة بكل متغير.

### مثال على شفرة المصدر للحصول على المتغيرات باستخدام Aspose.Words for .NET

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

لقد تعلمت الآن كيفية استرداد المتغيرات من مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك الوصول بسهولة إلى المتغيرات وعرضها من المستندات الخاصة بك.