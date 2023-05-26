---
title: مسح التحكم في المحتويات
linktitle: مسح التحكم في المحتويات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية مسح محتويات عنصر تحكم في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-sdt/clear-contents-control/
---

يوضح هذا البرنامج التعليمي كيفية مسح محتويات أداة معاملة خاصة في مستند Word باستخدام Aspose.Words for .NET. يؤدي مسح محتويات أداة معاملة خاصة إلى إزالة أي نص أو عقد فرعية داخل عنصر التحكم في المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واحصل على StructuredDocumentTag
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل. ثم ، استرجع ملف`StructuredDocumentTag` من الوثيقة. في هذا المثال ، نفترض أن المعاملة الخاصة والتفضيلية هي العقدة الفرعية الأولى في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: امسح محتويات StructuredDocumentTag
 امسح محتويات SDT باستخدام ملف`Clear` طريقة. يؤدي هذا إلى إزالة أي نص أو عقد فرعية داخل عنصر التحكم في المحتوى.

```csharp
sdt.Clear();
```

## الخطوة 4: احفظ المستند
احفظ المستند المعدل باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### مثال على شفرة المصدر لمسح التحكم في المحتويات باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

هذا كل شيء! لقد نجحت في مسح محتويات StructuredDocumentTag في مستند Word الخاص بك باستخدام Aspose.Words for .NET.