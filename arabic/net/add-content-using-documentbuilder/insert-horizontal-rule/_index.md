---
title: أدخل مسطرة أفقية
linktitle: أدخل مسطرة أفقية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج القواعد الأفقية في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

في هذا المثال الشامل ، ستتعلم كيفية إدراج قاعدة أفقية في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على إضافة قواعد أفقية إلى مستنداتك للفصل البصري والتنظيم.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل قاعدة أفقية
بعد ذلك ، استخدم طريقة Writeln لفئة DocumentBuilder لإضافة نص وصفي ثم أدخل قاعدة أفقية:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## الخطوة 3: احفظ المستند
بعد إدراج القاعدة الأفقية ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### مثال رمز مصدر لإدراج قاعدة أفقية باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدخال قاعدة أفقية باستخدام Aspose.Words for .NET:
تعتبر القواعد الأفقية مفيدة لسيناريوهات مختلفة ، مثل تقسيم الأقسام أو إنشاء فواصل مرئية أو تمييز المعلومات المهمة.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Insert a horizontal rule shape into the document.");
	builder.InsertHorizontalRule();

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
	
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج قاعدة أفقية في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن فصل المستندات وتنظيمها بصريًا باستخدام القواعد الأفقية.

