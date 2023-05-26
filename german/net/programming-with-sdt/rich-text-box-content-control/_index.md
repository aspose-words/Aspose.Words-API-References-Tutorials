---
title: التحكم في محتوى مربع نص منسق
linktitle: التحكم في محتوى مربع نص منسق
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء عنصر تحكم في محتوى مربع نص منسق في مستند Word باستخدام Aspose.Words for .NET مما يتيح تنسيق النص وتصميمه.
type: docs
weight: 10
url: /de/net/programming-with-sdt/rich-text-box-content-control/
---

يوضح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم محتوى مربع نص منسق في مستند Word باستخدام Aspose.Words for .NET. تسمح عناصر التحكم في محتوى مربع النص المنسق للمستخدمين بإدخال نص وتنسيقه باستخدام أنماط وخيارات تنسيق متنوعة.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و StructuredDocumentTag
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`StructuredDocumentTag` لتمثيل عنصر تحكم محتوى مربع النص المنسق. حدد`SdtType.RichText` كنوع و`MarkupLevel.Block` كمستوى الترميز لإنشاء مربع نص منسق على مستوى الكتلة.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## الخطوة 3: إنشاء وتنسيق محتوى نص منسق
قم بإنشاء فقرة وتشغيلها لتمثيل محتوى النص المنسق. اضبط النص وخيارات التنسيق مثل اللون والخط وما إلى ذلك.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## الخطوة 4: أضف محتوى Rich Text إلى عنصر التحكم في المحتوى
أضف الفقرة مع محتوى النص المنسق إلى ملف`ChildNodes` مجموعة من عنصر تحكم محتوى مربع نص منسق.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## الخطوة 5: قم بإلحاق Content Control بالمستند
 قم بإلحاق عنصر تحكم محتوى مربع النص المنسق بجسم المستند باستخدام ملف`AppendChild` طريقة نص القسم الأول من المستند.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### مثال على شفرة المصدر للتحكم في محتوى Rich Text Box باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
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