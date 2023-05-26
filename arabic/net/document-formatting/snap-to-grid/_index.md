---
title: المفاجئة إلى الشبكة
linktitle: المفاجئة إلى الشبكة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لشرح كود مصدر C # لميزة Snap to Grid باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/snap-to-grid/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام ميزة Snap to Grid مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: محاذاة الشبكة

سنقوم الآن بتطبيق محاذاة الشبكة على فقرة محددة والخط المستخدم في الفقرة. إليك الطريقة:

```csharp
// تمكين محاذاة الشبكة للفقرة
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// اكتب نصًا في الفقرة
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// قم بتمكين محاذاة الشبكة للخط المستخدم في الفقرة
par.Runs[0].Font.SnapToGrid = true;
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### مثال على شفرة المصدر لـ Snap To Grid باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة Snap to Grid مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// قم بتحسين التخطيط عند الكتابة بالأحرف الآسيوية.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

باستخدام هذا الرمز ، ستتمكن من محاذاة النص الخاص بك مع الشبكة وتحسين مظهر المستند باستخدام Aspose.Words for .NET.

