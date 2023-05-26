---
title: وثيقة المالك
linktitle: وثيقة المالك
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام مستند المالك في Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-node/owner-document/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه والذي يوضح كيفية استخدام وظائف المستندات الاحتكارية مع Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## الخطوة 2: قم بإنشاء مستند جديد
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 3: قم بإنشاء عقدة بمستند المالك
 عند إنشاء عقدة جديدة من أي نوع ، يجب عليك تمرير المستند إلى المنشئ. في هذا المثال ، نقوم بإنشاء عقدة فقرة جديدة باستخدام المستند`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## الخطوة 4: تحقق من العقدة الأصلية ومستند المالك
 الآن وقد أنشأنا عقدة الفقرة ، يمكننا التحقق مما إذا كانت تحتوي على عقدة أصلية وما إذا كان المستند المالك هو نفسه`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## الخطوة 5: تعديل خصائص العقدة ببيانات المستند
تسمح العلاقة بين العقدة والمستند بالوصول إلى الخصائص التي تشير إلى البيانات الخاصة بالمستند وتعديلها ، مثل الأنماط أو القوائم. في هذا المثال ، نقوم بتعيين اسم نمط الفقرة على أنه "العنوان 1".

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## الخطوة 6: أضف الفقرة إلى المستند
الآن يمكننا إضافة عقدة الفقرة إلى القسم الرئيسي من المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 7: تحقق من العقدة الأصلية بعد الإضافة
بعد إضافة الفقرة إلى المستند ، نتحقق مرة أخرى مما إذا كانت تحتوي الآن على عقدة أصلية.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### نموذج كود مصدر لمستند المالك مع Aspose.Words for .NET

```csharp
	Document doc = new Document();

	// يتطلب إنشاء عقدة جديدة من أي نوع تمرير مستند إلى المنشئ.
	Paragraph para = new Paragraph(doc);

	// عقدة الفقرة الجديدة ليس لها أصل حتى الآن.
	Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

	// لكن عقدة الفقرة تعرف وثيقتها.
	Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

	// تسمح لنا حقيقة أن العقدة تنتمي دائمًا إلى المستند بالوصول والتعديل
	// الخصائص التي تشير إلى البيانات على مستوى المستند ، مثل الأنماط أو القوائم.
	para.ParagraphFormat.StyleName = "Heading 1";

	// أضف الآن الفقرة إلى النص الرئيسي للقسم الأول.
	doc.FirstSection.Body.AppendChild(para);

	//أصبحت عقدة الفقرة الآن تابعة لعقدة النص الأساسي.
	Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
            
```



