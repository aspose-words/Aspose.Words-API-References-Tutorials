---
title: احصل على مجموعات المراجعة
linktitle: احصل على مجموعات المراجعة
second_title: Aspose.Words لمراجع .NET API
description: احصل على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-groups/
---

في هذا الدليل التدريجي ، سنخبرك بكيفية الحصول على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تصفح مجموعات المراجعة

بعد ذلك ، سنقوم بعمل حلقة عبر مجموعات المراجعة الموجودة في المستند ونعرض تفاصيلها ، مثل المؤلف ونوع المراجعة والنص المنقح.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### مثال على شفرة المصدر للحصول على مجموعات المراجعة باستخدام Aspose.Words for .NET

إليك التعليمات البرمجية المصدر الكاملة للحصول على مجموعات المراجعة في مستند باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach(RevisionGroup group in doc.Revisions.Groups)
	{
		 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
		 Console.WriteLine(group.Text);
	}
	
```


