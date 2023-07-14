---
title: قارن الخيارات
linktitle: قارن الخيارات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لشرح كود مصدر C # لميزة مقارنة الخيارات مع Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/compare-documents/compare-options/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استخدام ميزة مقارنة الخيارات مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: مقارنة المستندات بالخيارات المخصصة

 للبدء ، قم بتحميل وثيقتين للمقارنة. في هذا المثال ، سوف نستخدم الامتداد`Clone()` طريقة لإنشاء نسخة من المستند الأصلي. إليك الطريقة:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## الخطوة 2: تكوين خيارات المقارنة

 سنقوم الآن بتكوين خيارات المقارنة من خلال إنشاء ملف`CompareOptions` الكائن وتعيين الخصائص المختلفة حسب الحاجة. إليك الطريقة:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## الخطوة 3: مقارنة المستندات بالخيارات المخصصة

 سنستخدم الآن ملف`Compare()` طريقة تمرير الخيارات المخصصة لمقارنة الوثيقتين. ستحدد هذه الطريقة التغييرات في المستند الأصلي. إليك الطريقة:

```csharp
// قارن المستندات بالخيارات المخصصة
docA.Compare(docB, "user", DateTime.Now, options);

// تحقق مما إذا كانت المستندات متساوية
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### مثال على كود المصدر لمقارنة الخيارات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة مقارنة الخيارات مع Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

باستخدام هذا الرمز ، يمكنك مقارنة مستندين باستخدام خيارات مخصصة لتجاهل عناصر محددة عند المقارنة مع Aspose.Words for .NET.

