---
title: منشئ المستند إدراج إشارة مرجعية
linktitle: منشئ المستند إدراج إشارة مرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الإشارات المرجعية في مستندات Word باستخدام DocumentBuilder في Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

في هذا المثال الشامل ، ستتعلم كيفية إدراج الإشارات المرجعية في مستند Word باستخدام فئة DocumentBuilder في Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على إنشاء وإدارة الإشارات المرجعية داخل مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل إشارة مرجعية
بعد ذلك ، استخدم أساليب StartBookmark و EndBookmark لفئة DocumentBuilder لإدراج إشارة مرجعية في المستند. أدخل اسمًا فريدًا للإشارة المرجعية كمعامل:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## الخطوة 3: احفظ المستند
بعد إدراج الإشارة المرجعية ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### مثال رمز مصدر لـ DocumentBuilder إدراج إشارة مرجعية باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لإدخال إشارة مرجعية باستخدام فئة DocumentBuilder في Aspose.Words for .NET:

```csharp
   
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("FineBookmark");
	builder.Writeln("This is just a fine bookmark.");
	builder.EndBookmark("FineBookmark");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
	 
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج الإشارات المرجعية في مستند Word باستخدام فئة DocumentBuilder في Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إنشاء وإدارة الإشارات المرجعية داخل مستنداتك.

تعد الإشارات المرجعية مفيدة لسيناريوهات متنوعة ، مثل التنقل عبر مستندات كبيرة ، أو الرجوع إلى أقسام معينة ، أو معالجة المحتوى برمجيًا داخل المناطق التي تم وضع إشارة مرجعية عليها.

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.

