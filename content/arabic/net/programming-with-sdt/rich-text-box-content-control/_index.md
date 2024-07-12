---
title: التحكم في محتوى مربع النص المنسق
linktitle: التحكم في محتوى مربع النص المنسق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء عنصر تحكم محتوى مربع نص منسق في مستند Word باستخدام Aspose.Words for .NET لتمكين تنسيق النص وتصميمه.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/rich-text-box-content-control/
---

يوضح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم محتوى مربع نص منسق في مستند Word باستخدام Aspose.Words لـ .NET. تسمح عناصر التحكم في محتوى مربع النص المنسق للمستخدمين بإدخال النص وتنسيقه باستخدام أنماط وخيارات تنسيق متنوعة.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وStructuredDocumentTag
 إنشاء مثيل جديد لـ`Document` فئة و أ`StructuredDocumentTag` لتمثيل عنصر تحكم محتوى مربع النص المنسق. تحديد`SdtType.RichText` كنوع و`MarkupLevel.Block` كمستوى العلامات لإنشاء مربع نص منسق على مستوى الكتلة.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## الخطوة 3: إنشاء وتنسيق محتوى النص المنسق
قم بإنشاء فقرة وتشغيلها لتمثيل محتوى النص المنسق. اضبط خيارات النص والتنسيق مثل اللون والخط وما إلى ذلك.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## الخطوة 4: إضافة محتوى النص المنسق إلى عنصر التحكم في المحتوى
 قم بإضافة الفقرة التي تحتوي على محتوى النص المنسق إلى ملف`ChildNodes` مجموعة من عناصر التحكم في محتوى مربع النص المنسق.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## الخطوة 5: إلحاق التحكم في المحتوى بالمستند
 قم بإلحاق عنصر تحكم محتوى مربع النص المنسق بالنص الأساسي للمستند باستخدام`AppendChild` طريقة نص القسم الأول من الوثيقة.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### مثال على التعليمات البرمجية المصدر للتحكم في محتوى مربع النص المنسق باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

هذا كل شيء! لقد نجحت في إنشاء عنصر تحكم محتوى مربع نص منسق في مستند Word الخاص بك باستخدام Aspose.Words for .NET.