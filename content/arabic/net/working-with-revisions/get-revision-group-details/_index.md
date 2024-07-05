---
title: احصل على تفاصيل مجموعة المراجعة
linktitle: احصل على تفاصيل مجموعة المراجعة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: احصل على تفاصيل مجموعة المراجعة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-group-details/
---

في هذا الدليل التفصيلي، سنوضح لك كيفية الحصول على تفاصيل مجموعة من المراجعات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تصفح المراجعات

بعد ذلك، سنقوم بمراجعة المراجعات الموجودة في المستند وعرض تفاصيلها، مثل النوع والمؤلف والتاريخ والنص الذي تمت مراجعته.

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


### مثال على التعليمات البرمجية المصدر للحصول على تفاصيل مجموعة المراجعة باستخدام Aspose.Words لـ .NET

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

في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على تفاصيل مجموعة من المراجعات في مستند Word باستخدام Aspose.Words for .NET. باستخدام الحلقة والخصائص المناسبة، تمكنا من عرض تفاصيل مثل نوع المراجعة والمؤلف والتاريخ والنص الذي تمت مراجعته. يوفر Aspose.Words for .NET العديد من الميزات القوية لمعالجة مستندات Word، بما في ذلك إدارة المراجعة. يمكنك الآن استخدام هذه المعرفة للحصول على تفاصيل مجموعة المراجعة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني تحميل مستند يحتوي على مراجعات إلى Aspose.Words لـ .NET؟

 ج: استخدم`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف يحتوي على مراجعات. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني الحصول على تفاصيل مجموعة المراجعة في Aspose.Words لـ .NET؟

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

#### س: كيف يمكن التحقق مما إذا كانت المراجعة تنتمي إلى مجموعة في Aspose.Words for .NET؟

 ج: استخدم`Group` ملكية`Revision` كائن للتحقق مما إذا كانت المراجعة تنتمي إلى مجموعة. إذا`Group` الملكية هي`null`فهذا يعني أن المراجعة لا تنتمي إلى أي مجموعة.

```csharp
if (revision.Group != null)
{
      // المراجعة تنتمي إلى مجموعة
}
else
{
      // المراجعة لا تنتمي إلى أي مجموعة
}
```