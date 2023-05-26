---
title: خانة اختيار اكتب Content Control
linktitle: خانة اختيار اكتب Content Control
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء عنصر تحكم في المحتوى من نوع خانة اختيار في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/check-box-type-content-control/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم في محتوى نوع خانة اختيار في مستند Word باستخدام Aspose.Words for .NET. تتيح عناصر التحكم في محتوى خانة الاختيار للمستخدمين تحديد خانة اختيار أو مسحها داخل المستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` لبناء محتوى المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة خانة اختيار اكتب Content Control
 إنشاء`StructuredDocumentTag` مع`SdtType.Checkbox` لتمثيل عنصر تحكم محتوى خانة الاختيار. حدد`MarkupLevel.Inline` لوضعه داخل النص.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## الخطوة 4: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### مثال على شفرة المصدر لخانة الاختيار اكتب Content Control باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

هذا كل شيء! لقد نجحت في إنشاء عنصر تحكم في محتوى نوع خانة اختيار في مستند Word الخاص بك باستخدام Aspose.Words for .NET.