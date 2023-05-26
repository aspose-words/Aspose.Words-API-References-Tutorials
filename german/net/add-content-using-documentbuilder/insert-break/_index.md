---
title: أدخل فاصل
linktitle: أدخل فاصل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج فواصل الصفحات في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-break/
---

في هذا المثال الشامل ، ستتعلم كيفية إدراج فواصل الصفحات في مستند Word باستخدام طريقة InsertBreak في Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من التحكم في فواصل الصفحات داخل المستند الخاص بك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل المحتوى وفواصل الصفحات
بعد ذلك ، استخدم طريقة Writeln لفئة DocumentBuilder لإضافة محتوى إلى المستند. لإدراج فاصل صفحات ، استخدم الأسلوب InsertBreak مع المعلمة BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## الخطوة 3: احفظ المستند
بعد إدراج المحتوى وفواصل الصفحات ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### مثال على كود المصدر لإدراج استراحة باستخدام Aspose.Words for .NET
فيما يلي شفرة المصدر الكاملة لإدخال فواصل الصفحات باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("This is page 1.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 2.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 3.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
			
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.


## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج فواصل الصفحات في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن التحكم في ترقيم الصفحات وتخطيط المستند عن طريق إدراج فواصل الصفحات في المواضع المطلوبة.
