---
title: قسم متعدد
linktitle: قسم متعدد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استرداد علامات المستندات المنظمة متعددة الأقسام ومعالجتها في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/multi-section/
---

يشرح هذا البرنامج التعليمي كيفية العمل مع علامات المستندات المهيكلة متعددة الأقسام في مستند Word باستخدام Aspose.Words for .NET. يمكنك استرداد علامات القسم الموجودة في المستند ومعالجتها.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واسترجع العلامات متعددة الأقسام
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل. استرجع جميع عُقد بدء نطاق علامة المستند المهيكلة في المستند باستخدام امتداد`GetChildNodes` طريقة.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## الخطوة 3: معالجة العلامات متعددة الأقسام
كرر خلال مجموعة عقد بدء نطاق علامة المستند المنظمة. في هذا المثال ، نقوم ببساطة بطباعة عنوان كل علامة إلى وحدة التحكم. يمكنك إجراء مزيد من المعالجة بناءً على متطلباتك.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### مثال على شفرة المصدر للقسم المتعدد باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

هذا كل شيء! لقد نجحت في استرداد علامات المستندات المنظمة متعددة الأقسام ومعالجتها في مستند Word الخاص بك باستخدام Aspose.Words for .NET.