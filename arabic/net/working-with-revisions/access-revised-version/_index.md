---
title: الوصول إلى النسخة المنقحة
linktitle: الوصول إلى النسخة المنقحة
second_title: Aspose.Words لمراجع .NET API
description: قم بالوصول إلى نسخة منقحة من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/access-revised-version/
---

في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية الوصول إلى النسخة المنقحة من مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## الخطوة 2: الوصول إلى النسخة المعدلة

ننتقل الآن إلى النسخة المنقحة من الوثيقة.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## الخطوة 3: تصفح المراجعات

بعد ذلك ، سنقوم بتكرار المراجعات الموجودة في المستند ونعرض معلومات محددة للفقرات التي هي عناصر قائمة.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### مثال على شفرة المصدر لـ Access Revised Version باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للوصول إلى النسخة المعدلة من المستند باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// قم بالتبديل إلى النسخة المنقحة من المستند.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```


