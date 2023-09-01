---
title: ضبط لون التحكم في المحتوى
linktitle: ضبط لون التحكم في المحتوى
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين لون عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET، وتخصيص مظهره.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/set-content-control-color/
---

يشرح هذا البرنامج التعليمي كيفية تعيين لون عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET. يمكنك تخصيص مظهر عناصر التحكم في المحتوى عن طريق تغيير لونها.

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

## الخطوة 3: ضبط لون التحكم في المحتوى
 قم بتعيين لون عنصر التحكم في المحتوى عن طريق تعيين أ`Color` قيمة إلى`Color` خاصية علامة الوثيقة المنظمة. في هذا المثال، قمنا بتعيين اللون إلى اللون الأحمر.

```csharp
sdt.Color = Color.Red;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### مثال على التعليمات البرمجية المصدر لضبط لون التحكم في المحتوى باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

هذا كل شيء! لقد قمت بتعيين لون عنصر تحكم المحتوى في مستند Word الخاص بك بنجاح باستخدام Aspose.Words لـ .NET.