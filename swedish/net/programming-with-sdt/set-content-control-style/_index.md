---
title: تعيين نمط التحكم في المحتوى
linktitle: تعيين نمط التحكم في المحتوى
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين نمط عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET ، مع تطبيق تنسيق متسق.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/set-content-control-style/
---

يشرح هذا البرنامج التعليمي كيفية تعيين نمط عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET. يمكنك تطبيق أنماط محددة مسبقًا أو مخصصة على عناصر تحكم المحتوى من أجل تنسيق متناسق.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واسترجع عنصر التحكم في المحتوى
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل. استرجع عنصر التحكم في المحتوى المطلوب من المستند. في هذا المثال ، نفترض أن عنصر التحكم في المحتوى هو أول علامة منظمة للمستند في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: استرجع النمط وطبقه على التحكم في المحتوى
 استرجع النمط المطلوب من مجموعة أنماط المستند. في هذا المثال ، نسترجع نمط "اقتباس" باستخدام`StyleIdentifier.Quote` . بعد ذلك ، قم بتعيين النمط الذي تم استرداده إلى ملف`Style` خاصية علامة المستند المنظم.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Set Content Control Style باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

هذا كل شيء! لقد نجحت في تعيين نمط عنصر تحكم المحتوى في مستند Word الخاص بك باستخدام Aspose.Words for .NET.