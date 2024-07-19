---
title: الحالة الحالية لخانة الاختيار
linktitle: الحالة الحالية لخانة الاختيار
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد وتعيين الحالة الحالية لعنصر تحكم محتوى خانة الاختيار في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/current-state-of-check-box/
---

يشرح هذا البرنامج التعليمي كيفية استرداد وتعيين الحالة الحالية لعنصر تحكم محتوى خانة الاختيار في مستند Word باستخدام Aspose.Words for .NET. يمكنك تحديد أو إلغاء تحديد خانة الاختيار بناءً على حالتها الحالية.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل المستند واسترداد التحكم في محتوى خانة الاختيار
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. ثم قم باسترداد عنصر تحكم محتوى خانة الاختيار المطلوب من المستند. في هذا المثال، نفترض أن خانة الاختيار هي أول علامة مستند منظمة في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: قم بتحديد أو إلغاء تحديد خانة الاختيار بناءً على حالتها الحالية
 تحقق مما إذا كانت علامة المستند المنظمة التي تم استردادها من النوع`SdtType.Checkbox` . إذا كان الأمر كذلك، قم بتعيين`Checked` خاصية التحكم في المحتوى ل`true` لتحديد المربع. بخلاف ذلك، يمكنك تركها دون تحديد.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### مثال على التعليمات البرمجية المصدر لحالة خانة الاختيار الحالية باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// احصل على عنصر التحكم الأول في المحتوى من المستند.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

هذا كل شيء! لقد نجحت في استرداد وتعيين الحالة الحالية لعنصر تحكم محتوى خانة الاختيار في مستند Word الخاص بك باستخدام Aspose.Words for .NET.