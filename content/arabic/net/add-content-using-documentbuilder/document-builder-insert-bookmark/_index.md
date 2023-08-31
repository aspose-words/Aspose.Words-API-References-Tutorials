---
title: منشئ المستند إدراج إشارة مرجعية في مستند Word
linktitle: منشئ المستند إدراج إشارة مرجعية في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الإشارات المرجعية في مستندات Word باستخدام DocumentBuilder في Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
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

### التعليمات

#### س: هل يمكنني الحصول على إشارات مرجعية متعددة في مستند Word واحد؟

ج: إطلاقا! يمكنك إدراج العديد من الإشارات المرجعية حسب الحاجة في مستند Word باستخدام Aspose.Words for .NET. فقط تأكد من توفير أسماء فريدة لكل إشارة مرجعية لتجنب التعارضات.

#### س: هل يمكنني تعديل المحتوى داخل إشارة مرجعية بعد إدراجها؟

ج: نعم ، يمكنك بسهولة تعديل المحتوى داخل إشارة مرجعية بعد إدخاله. ما عليك سوى استخدام DocumentBuilder للانتقال إلى الإشارة المرجعية باسمها ثم معالجة المحتوى حسب الرغبة.

#### س: هل يمكن استخدام الإشارات المرجعية لاستخراج أقسام معينة من المستند برمجيًا؟

ج: بالتأكيد! تعتبر الإشارات المرجعية ذات قيمة لاستخراج أقسام معينة من المستند برمجيًا. باستخدام اسم الإشارة المرجعية ، يمكنك بسهولة تحديد واستخراج المحتوى داخل تلك المنطقة التي تم وضع إشارة مرجعية عليها.

#### س: هل من الممكن إضافة إشارات مرجعية إلى مستندات Word الحالية باستخدام Aspose.Words for .NET؟

ج: إطلاقا! يمكنك إضافة إشارات مرجعية إلى كل من مستندات Word الجديدة والحالية باستخدام Aspose.Words for .NET. ما عليك سوى فتح المستند الحالي ، وإدراج الإشارة المرجعية كما هو موضح في هذا البرنامج التعليمي ، وحفظ التغييرات.

#### س: هل يمكنني الانتقال إلى قسم تم وضع إشارة مرجعية عليه داخل المستند برمجيًا؟

ج: نعم ، يمكنك التنقل برمجيًا إلى قسم محدد تم وضع إشارة مرجعية عليه داخل المستند. باستخدام DocumentBuilder ، يمكنك تحديد موقع الإشارة المرجعية حسب اسمها وتنفيذ إجراءات متنوعة ، مثل إضافة محتوى جديد أو تطبيق التنسيق.