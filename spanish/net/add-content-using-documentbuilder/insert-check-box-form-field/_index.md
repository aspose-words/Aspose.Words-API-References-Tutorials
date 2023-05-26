---
title: أدخل حقل نموذج خانة اختيار
linktitle: أدخل حقل نموذج خانة اختيار
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقول نموذج خانة الاختيار في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج حقل نموذج خانة اختيار في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إضافة حقول نموذج مربعات الاختيار بخصائص قابلة للتخصيص إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل حقل نموذج خانة اختيار
بعد ذلك ، استخدم طريقة InsertCheckBox لفئة DocumentBuilder لإدراج حقل نموذج خانة اختيار. أدخل الاسم والحالة المحددة والحالة الافتراضية ومعلمات الحجم كوسائط:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## الخطوة 3: احفظ المستند
بعد إدراج حقل نموذج خانة الاختيار ، احفظ المستند في ملف باستخدام طريقة Save لفئة المستند:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### مثال كود المصدر لحقل نموذج خانة اختيار باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإدخال حقل نموذج مربع الاختيار باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertCheckBox("CheckBox", true, true, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
	
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج حقل نموذج خانة اختيار في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن تحسين مستنداتك باستخدام حقول نموذج مربعات الاختيار التفاعلية.
