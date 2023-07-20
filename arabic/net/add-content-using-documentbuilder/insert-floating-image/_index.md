---
title: إدراج صورة عائمة في مستند Word
linktitle: إدراج صورة عائمة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الصور العائمة في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-floating-image/
---
في هذا المثال الشامل ، ستتعلم كيفية إدراج صورة عائمة في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على إضافة صور مع خيارات تحديد الموضع والتفاف القابلة للتخصيص إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل صورة عائمة
بعد ذلك ، استخدم طريقة InsertImage لفئة DocumentBuilder لإدراج صورة عائمة. قم بتوفير مسار ملف الصورة والموضع الأفقي والرأسي النسبي والعرض والارتفاع وخيارات الالتفاف كمعلمات:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## الخطوة 3: احفظ المستند
بعد إدراج الصورة العائمة ، احفظ المستند في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## مثال على كود المصدر لإدراج صورة عائمة باستخدام Aspose.Words for .NET
إليك الكود المصدري الكامل لإدخال صورة عائمة باستخدام Aspose.Words for .NET:
تعد الصور العائمة مفيدة لسيناريوهات مختلفة ، مثل إضافة الشعارات أو الرسوم التوضيحية أو العناصر الزخرفية التي يمكن وضعها بشكل مستقل عن نص المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

تذكر أن تقوم بضبط الكود وفقًا لمتطلباتك المحددة ، بما في ذلك مسار ملف الصورة وخيارات الموضع والالتفاف المطلوبة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج صورة عائمة في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن تحسين مستنداتك بصور عائمة جذابة وقابلة للتخصيص.

### الأسئلة المتداولة حول إدراج الصورة العائمة في مستند Word

#### س: هل يمكنني إدراج عدة صور عائمة في مستند واحد؟

ج: بالتأكيد! يمكنك إدراج العديد من الصور العائمة حسب الحاجة في مستند Word باستخدام Aspose.Words for .NET. ما عليك سوى تكرار عملية الإدراج لإضافة صور متعددة جذابة بصريًا.

#### س: ما هي خيارات الالتفاف المتوفرة للصورة العائمة؟

ج: يوفر Aspose.Words for .NET خيارات التفاف متنوعة للصور العائمة ، بما في ذلك Square و Tight و Through و TopBottom و None. تحدد هذه الخيارات كيفية تفاعل النص مع الصورة العائمة.

#### س: هل يمكنني ضبط حجم الصورة العائمة؟

ج: إطلاقا! يمكنك تحديد عرض وارتفاع الصورة العائمة باستخدام المعلمات ذات الصلة في أسلوب InsertImage. يتيح لك ذلك التحكم في أبعاد الصورة وفقًا لتفضيلاتك في التصميم.

#### س: هل يمكنني وضع الصورة العائمة بالنسبة لعنصر معين في المستند؟

ج: نعم ، يتيح لك Aspose.Words for .NET وضع الصورة العائمة بالنسبة لعناصر محددة ، مثل الهامش أو الصفحة أو الفقرة أو الجدول. يمكنك اختيار معلمات الموضع الأفقي والعمودي المناسبة لتحقيق الموضع المطلوب.

#### س: هل Aspose.Words for .NET مناسب لتطبيقات سطح المكتب والويب؟

ج: نعم ، Aspose.Words for .NET مكتبة متعددة الاستخدامات مناسبة لكل من تطبيقات سطح المكتب والويب. سواء كنت تقوم ببناء تطبيق Windows أو نظام مستند إلى الويب ، يمكنك دمج المكتبة دون عناء.
