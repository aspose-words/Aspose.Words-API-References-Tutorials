---
title: احصل على تفاصيل مجموعة المراجعة
linktitle: احصل على تفاصيل مجموعة المراجعة
second_title: Aspose.Words لمراجع .NET API
description: احصل على تفاصيل مجموعة المراجعة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-group-details/
---

في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية الحصول على تفاصيل مجموعة المراجعات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تصفح المراجعات

بعد ذلك ، سنقوم بتكرار المراجعات الموجودة في المستند ونعرض تفاصيلها ، مثل النوع والمؤلف والتاريخ والنص المنقح.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### مثال على شفرة المصدر للحصول على تفاصيل مجموعة المراجعة باستخدام Aspose.Words for .NET

فيما يلي الكود المصدري الكامل للحصول على تفاصيل مجموعة المراجعات في مستند باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach (Revision revision in doc.Revisions)
	{
		 string groupText = revision.Group != null
			 ? "Revision group text: " + revision.Group.Text
			 : "The revision does not belong to any group";

		 Console.WriteLine("Type: " + revision.RevisionType);
		 Console.WriteLine("Author: " + revision.Author);
		 Console.WriteLine("Date: " + revision.DateTime);
		 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
		 Console.WriteLine(groupText);
	}
	
```

