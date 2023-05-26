---
title: أدخل حقل نموذج مربع التحرير والسرد
linktitle: أدخل حقل نموذج مربع التحرير والسرد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقول نموذج مربع التحرير والسرد في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

في هذا المثال الشامل ، ستتعلم كيفية إدراج حقل نموذج مربع تحرير وسرد في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إضافة حقول نموذج مربع التحرير والسرد بخصائص قابلة للتخصيص إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة الثانية: تحديد عناصر صندوق الكومبو
بعد ذلك ، حدد مصفوفة من العناصر لحقل نموذج مربع التحرير والسرد:

```csharp
string[] items = { "One", "Two", "Three" };
```

## الخطوة 3: أدخل حقل نموذج مربع تحرير وسرد
استخدم الأسلوب InsertComboBox لفئة DocumentBuilder لإدراج حقل نموذج مربع تحرير وسرد. أدخل الاسم ومجموعة العناصر والفهرس المحدد كمعلمات:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## الخطوة 4: احفظ المستند
بعد إدراج حقل نموذج مربع التحرير والسرد ، احفظ المستند في ملف باستخدام طريقة Save لفئة المستند:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### مثال رمز مصدر لإدراج حقل نموذج مربع تحرير وسرد باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدخال حقل نموذج مربع التحرير والسرد باستخدام Aspose.Words for .NET:

```csharp

	string[] items = { "One", "Two", "Three" };

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertComboBox("DropDown", items, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
	
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج حقل نموذج مربع تحرير وسرد في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن تحسين مستنداتك باستخدام حقول نموذج مربع التحرير والسرد التفاعلي.
