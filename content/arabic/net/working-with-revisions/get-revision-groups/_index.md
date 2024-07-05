---
title: الحصول على مجموعات المراجعة
linktitle: الحصول على مجموعات المراجعة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: احصل على مجموعات المراجعة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-groups/
---

في هذا الدليل خطوة بخطوة، سنخبرك بكيفية الحصول على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تصفح مجموعات المراجعة

بعد ذلك، سنمر عبر مجموعات المراجعة الموجودة في المستند ونعرض تفاصيلها، مثل المؤلف ونوع المراجعة والنص الذي تمت مراجعته.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### مثال على التعليمات البرمجية المصدر للحصول على مجموعات المراجعة باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل للحصول على مجموعات المراجعة في مستند باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على مجموعات المراجعة في مستند Word باستخدام Aspose.Words for .NET. لقد اتبعنا خطوات تحميل المستند وتصفح مجموعات المراجعة وعرض التفاصيل مثل المؤلف ونوع المراجعة. يمكنك الآن تطبيق هذه المعرفة لتحليل مراجعات مستند Word الخاص بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: كيفية تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيفية استعراض مجموعات المراجعة في مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Groups` خاصية الوثيقة`Revisions`كائن للحصول على مجموعة من مجموعات المراجعة. يمكنك بعد ذلك استخدام حلقة للتنقل خلال كل مجموعة مراجعة.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // قم بمعالجة كل مجموعة مراجعة هنا
}
```

#### س: كيف يمكن الحصول على مؤلف مجموعة المراجعة في Aspose.Words لـ .NET؟

 ج: استخدم`Author` ملكية`RevisionGroup` كائن للحصول على مؤلف مجموعة المراجعة.

```csharp
string author = group.Author;
```

#### س: كيف يمكن الحصول على نوع المراجعة لمجموعة المراجعة في Aspose.Words لـ .NET؟

 ج: استخدم`RevisionType` ملكية`RevisionGroup` كائن للحصول على نوع المراجعة للمجموعة.

```csharp
string revisionType = group.RevisionType;
```