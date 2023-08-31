---
title: قسم متعدد
linktitle: قسم متعدد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد علامات المستندات المنظمة متعددة الأقسام ومعالجتها في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/multi-section/
---

يشرح هذا البرنامج التعليمي كيفية العمل مع علامات المستندات المنظمة متعددة الأقسام في مستند Word باستخدام Aspose.Words for .NET. يمكنك استرداد ومعالجة علامات القسم الموجودة في المستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واسترجاع العلامات متعددة الأقسام
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. قم باسترداد كافة عقد بداية نطاق علامات المستند المنظم في المستند باستخدام`GetChildNodes` طريقة.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## الخطوة 3: معالجة العلامات متعددة الأقسام
قم بالتكرار من خلال مجموعة عقد بداية نطاق علامات المستند المنظم. في هذا المثال، نقوم ببساطة بطباعة عنوان كل علامة على وحدة التحكم. يمكنك إجراء المزيد من المعالجة بناءً على متطلباتك.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### مثال على التعليمات البرمجية المصدر للقسم المتعدد باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

هذا كل شيء! لقد نجحت في استرداد ومعالجة علامات المستندات المنظمة متعددة الأقسام في مستند Word الخاص بك باستخدام Aspose.Words for .NET.