---
title: تعيين لون التحكم في المحتوى
linktitle: تعيين لون التحكم في المحتوى
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين لون عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET ، مع تخصيص مظهره.
type: docs
weight: 10
url: /de/net/programming-with-sdt/set-content-control-color/
---

يشرح هذا البرنامج التعليمي كيفية تعيين لون عنصر تحكم المحتوى في مستند Word باستخدام Aspose.Words for .NET. يمكنك تخصيص مظهر عناصر تحكم المحتوى عن طريق تغيير لونها.

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

## الخطوة 3: اضبط لون التحكم في المحتوى
 اضبط لون عنصر تحكم المحتوى عن طريق تعيين ملف`Color` قيمة`Color` خاصية علامة المستند المنظم. في هذا المثال ، قمنا بتعيين اللون إلى الأحمر.

```csharp
sdt.Color = Color.Red;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### مثال على شفرة المصدر لـ Set Content Control Color باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

هذا كل شيء! لقد نجحت في تعيين لون عنصر تحكم المحتوى في مستند Word الخاص بك باستخدام Aspose.Words for .NET.