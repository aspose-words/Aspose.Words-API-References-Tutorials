---
title: مجموعة فواصل أسطر الطباعة الآسيوية
linktitle: مجموعة فواصل أسطر الطباعة الآسيوية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام مجموعة فواصل أسطر الطباعة الآسيوية مع Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/asian-typography-line-break-group/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية استخدام ميزة مجموعة فواصل أسطر الطباعة الآسيوية مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر وتطبيق تغييرات التنسيق.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## الخطوة 2: إعداد الطباعة الآسيوية

سنقوم الآن بتكوين إعدادات الطباعة الآسيوية للفقرة الأولى من المستند. إليك الطريقة:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### مثال على شفرة المصدر لمجموعة خطوط الطباعة الآسيوية باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة Asian Typography Line Break Group مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
باستخدام هذا الرمز ، ستتمكن من تطبيق مجموعة فواصل أسطر الطباعة الآسيوية باستخدام Aspose.Words for .NET.

