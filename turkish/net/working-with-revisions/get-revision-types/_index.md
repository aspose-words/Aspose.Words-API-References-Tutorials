---
title: احصل على أنواع المراجعة
linktitle: احصل على أنواع المراجعة
second_title: Aspose.Words لمراجع .NET API
description: احصل على أنواع المراجعات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-types/
---

في هذا الدليل التدريجي ، سنخبرك بكيفية الحصول على أنواع المراجعات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة الثانية: تصفح الفقرات

بعد ذلك ، سنتصفح فقرات المستند ونتحقق من أنواع المراجعات المرتبطة بكل فقرة.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### مثال على شفرة المصدر للحصول على أنواع المراجعة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للحصول على أنواع المراجعة في مستند باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
	for (int i = 0; i < paragraphs.Count; i++)
	{
		 if (paragraphs[i].IsMoveFromRevision)
			 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
		 if (paragraphs[i].IsMoveToRevision)
			 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
	}

```
