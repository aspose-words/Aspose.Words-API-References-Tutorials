---
title: خانة الاختيار الحالية
linktitle: خانة الاختيار الحالية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استرداد الحالة الحالية لعنصر تحكم محتوى خانة الاختيار وتعيينه في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/current-state-of-check-box/
---

يشرح هذا البرنامج التعليمي كيفية استرداد الحالة الحالية لعنصر تحكم محتوى مربع الاختيار وتعيينه في مستند Word باستخدام Aspose.Words for .NET. يمكنك تحديد أو إلغاء تحديد خانة الاختيار بناءً على حالتها الحالية.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند واسترجع عنصر التحكم في محتوى خانة الاختيار
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل. ثم قم باسترداد عنصر التحكم في محتوى خانة الاختيار المطلوب من المستند. في هذا المثال ، نفترض أن خانة الاختيار هي علامة المستند المهيكلة الأولى في المستند.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## الخطوة 3: حدد أو ألغِ تحديد خانة الاختيار بناءً على حالتها الحالية
 تحقق مما إذا كانت علامة المستند المهيكلة المستردة من النوع`SdtType.Checkbox` . إذا كان الأمر كذلك ، فاضبط ملف`Checked` ملكية التحكم في المحتوى إلى`true` لتحديد المربع. خلاف ذلك ، يمكنك تركه دون رادع.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save`طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### مثال على شفرة المصدر لـ Current State Of Check Box باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// احصل على أول عنصر تحكم في المحتوى من المستند.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

هذا كل شيء! لقد نجحت في استرداد الحالة الحالية لعنصر تحكم محتوى مربع الاختيار في مستند Word الخاص بك وتعيينه باستخدام Aspose.Words for .NET.