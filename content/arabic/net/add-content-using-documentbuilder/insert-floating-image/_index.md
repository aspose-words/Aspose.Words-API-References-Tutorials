---
title: إدراج صورة عائمة في مستند Word
linktitle: إدراج صورة عائمة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج صور عائمة في مستندات Word باستخدام Aspose.Words لـ .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-floating-image/
---
في هذا المثال الشامل، ستتعلم كيفية إدراج صورة عائمة في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إضافة صور ذات خيارات تحديد موضع والتفاف قابلة للتخصيص إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد وDocumentBuilder
للبدء، قم بإنشاء مستند جديد باستخدام فئة Document وقم بتهيئة كائن DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج صورة عائمة
بعد ذلك، استخدم طريقة InsertImage لفئة DocumentBuilder لإدراج صورة عائمة. قم بتوفير مسار ملف الصورة، والموضع الأفقي والرأسي النسبي، والعرض، والارتفاع، وخيارات الالتفاف كمعلمات:

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
بعد إدراج الصورة العائمة، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## مثال على كود المصدر لإدراج صورة عائمة باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدراج صورة عائمة باستخدام Aspose.Words لـ .NET:
تعد الصور العائمة مفيدة لسيناريوهات مختلفة، مثل إضافة الشعارات أو الرسوم التوضيحية أو العناصر الزخرفية التي يمكن وضعها بشكل مستقل عن نص المستند.

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

تذكر أن تقوم بضبط الكود وفقًا لمتطلباتك المحددة، بما في ذلك مسار ملف الصورة وخيارات الموضع والالتفاف المطلوبة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج صورة عائمة في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن تحسين مستنداتك باستخدام صور عائمة جذابة بصريًا وقابلة للتخصيص.

### الأسئلة الشائعة حول إدراج صورة عائمة في مستند Word

#### س: هل يمكنني إدراج عدة صور عائمة في مستند واحد؟

ج: بالتأكيد! يمكنك إدراج أي عدد تريده من الصور العائمة في مستند Word باستخدام Aspose.Words لـ .NET. ما عليك سوى تكرار عملية الإدراج لإضافة عدة صور جذابة.

#### س: ما هي خيارات الالتفاف المتوفرة للصورة العائمة؟

ج: يوفر Aspose.Words for .NET خيارات التفاف متنوعة للصور العائمة، بما في ذلك Square وTight وThrough وTopBottom وNone. تحدد هذه الخيارات كيفية تفاعل النص مع الصورة العائمة.

#### س: هل يمكنني ضبط حجم الصورة العائمة؟

ج: بالتأكيد! يمكنك تحديد عرض الصورة العائمة وارتفاعها باستخدام المعلمات المعنية في طريقة InsertImage. يتيح لك ذلك التحكم في أبعاد الصورة وفقًا لتفضيلات التصميم الخاصة بك.

#### س: هل يمكنني وضع الصورة العائمة بالنسبة لعنصر محدد في المستند؟

ج: نعم، يسمح لك Aspose.Words for .NET بوضع الصورة العائمة بالنسبة لعناصر محددة، مثل الهامش أو الصفحة أو الفقرة أو الجدول. يمكنك اختيار معلمات الموضع الأفقي والرأسي المناسبة لتحقيق الموضع المطلوب.

#### س: هل Aspose.Words for .NET مناسب لكل من تطبيقات سطح المكتب والويب؟

ج: نعم، Aspose.Words for .NET عبارة عن مكتبة متعددة الاستخدامات ومناسبة لكل من تطبيقات سطح المكتب والويب. سواء كنت تقوم بإنشاء تطبيق Windows أو نظام قائم على الويب، يمكنك دمج المكتبة دون عناء.
