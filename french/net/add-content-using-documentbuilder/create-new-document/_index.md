---
title: قم بإنشاء مستند جديد
linktitle: قم بإنشاء مستند جديد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء مستند Word جديد وإضافة محتوى باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/create-new-document/
---

في هذا البرنامج التعليمي خطوة بخطوة ، ستتعلم كيفية إنشاء مستند Word جديد من البداية باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إنشاء مستند جديد وإضافة محتوى إليه باستخدام فئة DocumentBuilder.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بإنشاء مستند جديد
للبدء ، أنشئ مستندًا جديدًا باستخدام فئة المستند:

```csharp
Document doc = new Document();
```

## الخطوة الثانية: إضافة محتوى إلى المستند
بعد ذلك ، استخدم كائن DocumentBuilder لإضافة محتوى إلى المستند. قم بتهيئة DocumentBuilder بالمستند الذي تم إنشاؤه حديثًا:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## الخطوة 3: احفظ المستند
بعد إضافة المحتوى المطلوب ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## مثال كود المصدر لإنشاء مستند جديد باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لإنشاء مستند جديد باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();

// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إنشاء مستند Word جديد باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إنشاء مستندات جديدة برمجيًا وإضافة محتوى إليها باستخدام فئة DocumentBuilder.

يمكنك الآن إنشاء مستندات Word وتخصيصها بثقة وفقًا لمتطلباتك المحددة.

### مثال على شفرة المصدر لإنشاء مستند جديد باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();

// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

تذكر أن تقوم بضبط مسار الملف واسمه في الكود لحفظ المستند في الموقع المطلوب على نظامك.

