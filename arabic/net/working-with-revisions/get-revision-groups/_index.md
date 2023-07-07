---
title: احصل على مجموعات المراجعة
linktitle: احصل على مجموعات المراجعة
second_title: Aspose.Words لمراجع .NET API
description: احصل على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-groups/
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET. لقد اتبعنا الخطوات لتحميل المستند واستعراض مجموعات المراجعة ، وعرض التفاصيل مثل المؤلف ونوع المراجعة. يمكنك الآن تطبيق هذه المعرفة لتحليل المراجعات لوثيقة Word الخاصة بك باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكن تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم ملف`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني تصفح مجموعات المراجعة في مستند في Aspose.Words for .NET؟

 ج: استخدم ملف`Groups` ملكية المستند`Revisions` كائن للحصول على مجموعة من مجموعات المراجعة. يمكنك بعد ذلك استخدام حلقة للتكرار خلال كل مجموعة مراجعة.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // معالجة كل مجموعة مراجعة هنا
}
```

#### س: كيف تحصل على مؤلف مجموعة المراجعة في Aspose.Words for .NET؟

 ج: استخدم ملف`Author` ممتلكات`RevisionGroup` كائن للحصول على مؤلف مجموعة المراجعة.

```csharp
string author = group.Author;
```

#### س: كيف تحصل على نوع المراجعة لمجموعة المراجعة في Aspose.Words for .NET؟

 ج: استخدم ملف`RevisionType` ممتلكات`RevisionGroup`كائن للحصول على نوع المراجعة للمجموعة.

```csharp
string revisionType = group.RevisionType;
```