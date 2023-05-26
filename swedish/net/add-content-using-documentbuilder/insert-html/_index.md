---
title: أدخل Html
linktitle: أدخل Html
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج محتوى HTML في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-html/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج محتوى HTML في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إضافة عناصر HTML وتنسيقات وأنماط إلى مستندات Word الخاصة بك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل محتوى HTML
بعد ذلك ، استخدم الأسلوب InsertHtml لفئة DocumentBuilder لإدراج محتوى HTML في المستند. يمكنك تضمين علامات HTML والسمات والأنماط ضمن سلسلة HTML:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## الخطوة 3: احفظ المستند
بعد إدخال محتوى HTML ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## مثال على كود المصدر لإدراج HTML باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإدخال محتوى HTML في مستند Word باستخدام Aspose.Words for .NET:
هذه الميزة مفيدة بشكل خاص عندما يكون لديك محتوى HTML موجود تريد تضمينه في مستندات Word الخاصة بك مع الحفاظ على التنسيق الأصلي والتخطيط.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHtml(
		"<P align='right'>Paragraph right</P>" +
		"<b>Implicit paragraph left</b>" +
		"<div align='center'>Div center</div>" +
		"<h1 align='left'>Heading 1 left.</h1>");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
	
```

تذكر أن تقوم بتعديل الكود وفقًا لمحتوى ومتطلبات HTML الخاصة بك. تأكد من أن HTML منسق بشكل جيد ومتوافق مع Aspose.Words for .NET.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج محتوى HTML في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن دمج عناصر HTML والتنسيق والأنماط في مستندات Word الخاصة بك.


