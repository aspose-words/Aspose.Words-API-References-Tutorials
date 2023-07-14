---
title: موضع المؤشر
linktitle: موضع المؤشر
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استرداد موضع المؤشر في مستند Word باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/cursor-position/
---

في هذا المثال خطوة بخطوة ، ستتعرف على موضع المؤشر في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من استرداد العقدة والفقرة الحالية حيث يتم وضع المؤشر في المستند.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: الوصول إلى العقدة الحالية والفقرة
بعد ذلك ، استرجع العقدة والفقرة الحالية حيث تم وضع المؤشر. يمكن تحقيق ذلك باستخدام خصائص CurrentNode و CurrentParagraph لفئة DocumentBuilder:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## الخطوة 3: استرداد معلومات موضع المؤشر
الآن ، يمكنك استرداد المعلومات حول موضع المؤشر. في مقتطف الكود التالي ، نطبع نص الفقرة الحالية:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### مثال رمز مصدر لموقع المؤشر باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لفهم موضع المؤشر باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية التعامل مع موضع المؤشر في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن استرداد العقدة والفقرة الحالية حيث يتم وضع المؤشر في المستند.

يعد فهم موضع المؤشر مفيدًا للعديد من السيناريوهات ، مثل معالجة محتوى المستند استنادًا إلى موقع المؤشر أو تنفيذ ميزات التحرير المخصصة.

