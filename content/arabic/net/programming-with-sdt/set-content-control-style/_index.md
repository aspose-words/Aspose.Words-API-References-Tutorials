---
title: ضبط نمط التحكم في المحتوى
linktitle: ضبط نمط التحكم في المحتوى
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين نمط عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words لـ .NET، مع تطبيق تنسيق متسق.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/set-content-control-style/
---

يشرح هذا البرنامج التعليمي كيفية تعيين نمط عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET. يمكنك تطبيق أنماط محددة مسبقًا أو مخصصة على عناصر التحكم في المحتوى للحصول على تنسيق متسق.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل المستند واسترداد التحكم في المحتوى
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. استرداد عنصر التحكم في المحتوى المطلوب من المستند. في هذا المثال، نفترض أن عنصر التحكم في المحتوى هو أول علامة مستند منظمة في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: استرداد النمط وتطبيقه على التحكم في المحتوى
 قم باسترجاع النمط المطلوب من مجموعة أنماط المستند. في هذا المثال، نقوم باسترداد نمط "الاقتباس" باستخدام`StyleIdentifier.Quote` . ثم قم بتعيين النمط المسترد إلى`Style` خاصية علامة الوثيقة المنظمة.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### مثال على التعليمات البرمجية المصدر لتعيين نمط التحكم في المحتوى باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

هذا كل شيء! لقد نجحت في تعيين نمط عنصر تحكم المحتوى في مستند Word الخاص بك باستخدام Aspose.Words for .NET.