---
title: إدراج صورة مضمنة في مستند Word
linktitle: إدراج صورة مضمنة في مستند Word
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

### الأسئلة الشائعة لإدراج صورة مضمنة في مستند Word

#### س: هل يمكنني تغيير حجم الصور المضمنة داخل مستند Word؟

ج: نعم ، يمكنك تغيير حجم الصور المضمنة باستخدام Aspose.Words for .NET. بعد إدراج الصورة ، يمكنك معالجة حجمها عن طريق ضبط خصائص العرض والارتفاع لكائن الشكل الذي يمثل الصورة.

#### س: هل من الممكن إضافة نص بديل إلى الصور المضمنة لأغراض الوصول؟

ج: نعم ، يمكنك إضافة نص بديل إلى الصور المضمنة لتحسين إمكانية الوصول. يدعم Aspose.Words for .NET إضافة نص بديل إلى الصور ، مما يسمح لقارئات الشاشة والتقنيات المساعدة الأخرى لوصف محتوى الصورة للمستخدمين ضعاف البصر.

#### س: هل يمكنني تطبيق التنسيق أو الأنماط على الصور المضمنة؟

ج: إطلاقا! يوفر Aspose.Words for .NET خيارات تنسيق شاملة للصور المضمنة. يمكنك تطبيق العديد من الأنماط والحدود والتأثيرات وسمات التنسيق الأخرى على الصور لمطابقة التصميم المرئي للمستند.

#### س: هل يدعم Aspose.Words for .NET إدراج الصور من مجموعة دفق أو بايت؟

ج: نعم ، يمكنك إدراج صور مضمنة من التدفقات أو مصفوفات البايت باستخدام Aspose.Words for .NET. يتيح لك هذا العمل مع الصور التي تم تحميلها من مصادر خارجية أو الصور التي تم إنشاؤها ديناميكيًا.

#### س: هل يمكنني إدراج الصور في مواضع محددة داخل محتوى النص؟

ج: نعم ، توفر فئة DocumentBuilder في Aspose.Words for .NET تحكمًا دقيقًا في موضع إدراج الصور المضمنة. يمكنك تحديد الموقع الدقيق داخل النص حيث يجب إدراج الصورة.