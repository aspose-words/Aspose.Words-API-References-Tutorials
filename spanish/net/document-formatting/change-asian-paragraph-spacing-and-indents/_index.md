---
title: تغيير تباعد الفقرات الآسيوية والمسافات البادئة
linktitle: تغيير تباعد الفقرات الآسيوية والمسافات البادئة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تغيير تباعد الفقرات الآسيوية والمسافات البادئة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## الخطوة 2: تغيير تباعد الفقرات والمسافات البادئة

سنقوم الآن بتعديل المسافات والمسافات البادئة للفقرة الأولى من الوثيقة الآسيوية. إليك الطريقة:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // تحديث ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // تحديث ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // تحديث ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // قم بتحديث ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // تحديث ParagraphFormat.SpaceAfter
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### مثال على شفرة المصدر لتغيير المسافات والمسافات البادئة للفقرات الآسيوية باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة تحرير تباعد الفقرات والمسافات البادئة الآسيوية باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // سيتم تحديث ParagraphFormat.LeftIndent
	format.CharacterUnitRightIndent = 10;      // سيتم تحديث تنسيق الفقرة
	format.CharacterUnitFirstLineIndent = 20;  //سيتم تحديث ParagraphFormat.FirstLineIndent
	format.LineUnitBefore = 5;                 // سيتم تحديث ParagraphFormat.SpaceBefore
	format.LineUnitAfter = 10;                 // سيتم تحديث ParagraphFormat.SpaceAfter

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

باستخدام هذا الرمز ، ستتمكن من تغيير المسافات والمسافات البادئة لفقرة آسيوية باستخدام Aspose.Words for .NET.

