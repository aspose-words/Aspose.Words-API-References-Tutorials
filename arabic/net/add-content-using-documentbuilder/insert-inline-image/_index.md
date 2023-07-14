---
title: إدراج صورة مضمنة
linktitle: إدراج صورة مضمنة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الصور المضمنة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-inline-image/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج الصور المضمنة في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إضافة الصور مباشرة إلى نص مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل صورة مضمنة
بعد ذلك ، استخدم طريقة InsertImage لفئة DocumentBuilder لإدراج صورة مضمنة في المستند. قم بتوفير مسار ملف الصورة كمعامل:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## الخطوة 3: احفظ المستند
بعد إدراج الصورة المضمنة ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### مثال على كود المصدر لإدراج صورة مضمنة باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإدخال صورة مضمنة باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج الصور المضمنة في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إضافة الصور بسلاسة داخل نص المستندات الخاصة بك.

تعد الصور المضمنة مفيدة للعديد من السيناريوهات ، مثل إضافة الرسوم التوضيحية أو الشعارات أو العناصر المرئية الأخرى مباشرةً في تدفق المستند.
