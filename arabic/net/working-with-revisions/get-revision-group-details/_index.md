---
title: احصل على تفاصيل مجموعة المراجعة
linktitle: احصل على تفاصيل مجموعة المراجعة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: احصل على تفاصيل مجموعة المراجعة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-group-details/
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على تفاصيل مجموعة المراجعات في مستند Word باستخدام Aspose.Words for .NET. باستخدام حلقة والخصائص المناسبة ، تمكنا من عرض تفاصيل مثل نوع المراجعة والمؤلف والتاريخ والنص الذي تمت مراجعته. يوفر Aspose.Words for .NET العديد من الميزات القوية لمعالجة مستندات Word ، بما في ذلك إدارة المراجعة. يمكنك الآن استخدام هذه المعرفة للحصول على تفاصيل مجموعة المراجعة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكنني تحميل مستند يحتوي على مراجعات في Aspose.Words for .NET؟

 ج: استخدم ملف`Document`فئة Aspose.Words for .NET لتحميل مستند من ملف يحتوي على مراجعات. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني الحصول على تفاصيل مجموعة المراجعة في Aspose.Words for .NET؟

 ج: راجع مراجعات المستند باستخدام حلقة وقم بالوصول إلى خصائص كل مراجعة للحصول على التفاصيل التي تريدها. يمكنك استخدام ال`RevisionType`, `Author`, `DateTime` و`ParentNode` للحصول على نوع المراجعة والمؤلف والتاريخ والنص المنقح على التوالي.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### س: كيف تتحقق مما إذا كانت المراجعة تنتمي إلى مجموعة في Aspose.Words for .NET؟

 ج: استخدم ملف`Group` ممتلكات`Revision` للتحقق مما إذا كانت المراجعة تنتمي إلى مجموعة. إذا كان`Group` الملكية`null`، فهذا يعني أن المراجعة لا تنتمي إلى أي مجموعة.

```csharp
if (revision.Group != null)
{
      // المراجعة تنتمي إلى مجموعة
}
else
{
      // لا تنتمي المراجعة إلى أي مجموعة
}
```