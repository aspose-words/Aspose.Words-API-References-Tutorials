---
title: مسح التحكم في المحتويات
linktitle: مسح التحكم في المحتويات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية مسح محتويات عنصر التحكم في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/clear-contents-control/
---

يوضح هذا البرنامج التعليمي كيفية مسح محتويات SDT في مستند Word باستخدام Aspose.Words لـ .NET. يؤدي مسح محتويات SDT إلى إزالة أي عقد نصية أو فرعية ضمن عنصر التحكم في المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واحصل على StructuredDocumentTag
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. ومن ثم استرجاع المطلوب`StructuredDocumentTag`من الوثيقة. في هذا المثال، نفترض أن SDT هي العقدة الفرعية الأولى في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: امسح محتويات StructuredDocumentTag
 امسح محتويات SDT باستخدام`Clear` طريقة. يؤدي هذا إلى إزالة أي عقد نصية أو فرعية ضمن عنصر تحكم المحتوى.

```csharp
sdt.Clear();
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل باستخدام`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### مثال على التعليمات البرمجية المصدر لمسح التحكم في المحتويات باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

هذا كل شيء! لقد نجحت في مسح محتويات StructuredDocumentTag في مستند Word الخاص بك باستخدام Aspose.Words for .NET.