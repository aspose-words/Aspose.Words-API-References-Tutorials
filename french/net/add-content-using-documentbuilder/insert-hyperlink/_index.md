---
title: أدخل ارتباط تشعبي
linktitle: أدخل ارتباط تشعبي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الارتباطات التشعبية في مستندات Word باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-hyperlink/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج الارتباطات التشعبية في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إضافة ارتباطات تشعبية قابلة للنقر إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل ارتباط تشعبي
بعد ذلك ، استخدم طريقة الكتابة الخاصة بفئة DocumentBuilder لإضافة نص وتنسيق الارتباط التشعبي عن طريق تعيين خصائص اللون والتسطير:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com "، خطأ) ؛

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## الخطوة 3: احفظ المستند
بعد إدراج الارتباط التشعبي ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## مثال رمز مصدر لإدراج ارتباط تشعبي باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لإدخال ارتباط تشعبي باستخدام Aspose.Words for .NET:

تعتبر الارتباطات التشعبية طريقة فعالة لتحسين تفاعل وفائدة مستندات Word الخاصة بك. يمكن استخدامها للإشارة إلى موارد خارجية أو توفير معلومات إضافية أو إنشاء عناصر تنقل داخل المستند.

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Please make sure to visit ");
	builder.Font.Color = Color.Blue;
	builder.Font.Underline = Underline.Single;
	
	builder.InsertHyperlink("Aspose Website", "http://www.aspose.com "، خطأ) ؛
	
	builder.Font.ClearFormatting();
	builder.Write(" for more information.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك المحددة ، بما في ذلك نص الارتباط التشعبي وعنوان URL. قم بتحسينه بالتنسيق أو الوظائف الإضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج الارتباطات التشعبية في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إضافة ارتباطات تشعبية قابلة للنقر إلى مستنداتك ، وتوجيه القراء إلى مواقع ويب خارجية أو عناوين URL محددة.

