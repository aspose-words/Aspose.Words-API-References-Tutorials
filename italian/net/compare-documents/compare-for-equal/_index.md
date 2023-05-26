---
title: قارن للحصول على Equal
linktitle: قارن للحصول على Equal
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # لميزة "المقارنة لـ Equals مع Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/compare-documents/compare-for-equal/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام ميزة مقارنة مع Equal مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: مقارنة المستندات

 للبدء ، قم بتحميل وثيقتين للمقارنة. في هذا المثال ، سوف نستخدم الامتداد`Clone()` طريقة لإنشاء نسخة من المستند الأصلي. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## الخطوة 2: مقارنة المستندات

 سنستخدم الآن ملف`Compare()` طريقة للمقارنة بين الوثيقتين. ستحدد هذه الطريقة التغييرات في المستند الأصلي. إليك الطريقة:

```csharp
// قارن المستندات
docA.Compare(docB, "user", DateTime.Now);

// تحقق مما إذا كانت المستندات متساوية
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### مثال على شفرة المصدر لـ Compare For Equal باستخدام Aspose.Words for .NET

فيما يلي الكود المصدري الكامل لميزة Compare for Equals مع Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// يحتوي DocA الآن على تغييرات كمراجعات.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

باستخدام هذا الرمز ، ستتمكن من مقارنة مستندين وتحديد ما إذا كانا متطابقين باستخدام Aspose.Words for .NET.

