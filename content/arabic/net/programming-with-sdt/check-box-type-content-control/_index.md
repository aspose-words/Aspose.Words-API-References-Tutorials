---
title: حدد خانة الاختيار للتحكم في محتوى النوع
linktitle: حدد خانة الاختيار للتحكم في محتوى النوع
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء عنصر تحكم في محتوى نوع خانة الاختيار في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/check-box-type-content-control/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم في محتوى نوع خانة الاختيار في مستند Word باستخدام Aspose.Words for .NET. تسمح عناصر التحكم في محتوى خانة الاختيار للمستخدمين بتحديد أو إلغاء تحديد خانة اختيار داخل المستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` لبناء محتوى الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة عنصر تحكم في محتوى نوع خانة الاختيار
 إنشاء`StructuredDocumentTag` مع`SdtType.Checkbox` لتمثيل التحكم في محتوى خانة الاختيار. تحديد`MarkupLevel.Inline` لوضعه داخل النص.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## الخطوة 4: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### مثال على التعليمات البرمجية المصدر للتحكم في محتوى نوع خانة الاختيار باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

هذا كل شيء! لقد نجحت في إنشاء عنصر تحكم في محتوى نوع خانة الاختيار في مستند Word الخاص بك باستخدام Aspose.Words for .NET.