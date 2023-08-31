---
title: تنسيق القاعدة الأفقية في مستند Word
linktitle: تنسيق القاعدة الأفقية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنسيق القواعد الأفقية في مستندات Word باستخدام Aspose.Words لـ .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/horizontal-rule-format/
---
في هذا المثال الشامل، ستتعلم كيفية تنسيق قاعدة أفقية في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستكون قادرًا على تخصيص المحاذاة والعرض والارتفاع واللون والخصائص الأخرى للقاعدة الأفقية.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء DocumentBuilder وإدراج قاعدة أفقية
للبدء، أنشئ كائن DocumentBuilder واستخدم التابع InsertHorizontalRule لإدراج قاعدة أفقية:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## الخطوة 2: الوصول إلى تنسيق القاعدة الأفقية
بعد ذلك، قم بالوصول إلى خاصية HorizontalRuleFormat لكائن الشكل لاسترداد خيارات التنسيق:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## الخطوة 3: تخصيص خيارات التنسيق
الآن، يمكنك تخصيص خيارات التنسيق المتنوعة للقاعدة الأفقية. على سبيل المثال، يمكنك ضبط المحاذاة والعرض والارتفاع واللون والتظليل:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## الخطوة 4: احفظ المستند
بعد تنسيق القاعدة الأفقية، احفظ المستند في ملف باستخدام طريقة Save لكائن Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### مثال على كود المصدر لتنسيق القاعدة الأفقية باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لتنسيق القاعدة الأفقية باستخدام Aspose.Words لـ .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

تذكر تعديل الكود وفقًا لمتطلباتك المحددة وتعزيزه بوظائف إضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تنسيق قاعدة أفقية في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك الآن تخصيص مظهر القواعد الأفقية لتحسين التخطيط المرئي للمستند.

قم بتجربة خيارات التنسيق المختلفة لتحقيق النمط والتأثير المطلوبين لقواعدك الأفقية.

### الأسئلة الشائعة حول تنسيق القاعدة الأفقية في مستند Word

#### س: هل يمكنني تطبيق ألوان مختلفة على القاعدة الأفقية؟

ج: بالتأكيد! باستخدام Aspose.Words for .NET، يمكنك بسهولة تخصيص لون القاعدة الأفقية عن طريق تعيين خاصية اللون إلى قيمة اللون المطلوبة. يتيح لك ذلك مطابقة القاعدة الأفقية مع التصميم العام للمستند الخاص بك.

#### س: هل من الممكن تعديل عرض وارتفاع القاعدة الأفقية؟

ج: نعم، لديك السيطرة الكاملة على عرض وارتفاع القاعدة الأفقية. من خلال تعديل خصائص WidthPercent وHeight، يمكنك تحقيق الأبعاد المطلوبة للقاعدة الأفقية.

#### س: هل يمكنني تغيير محاذاة المسطرة الأفقية داخل المستند؟

ج: بالتأكيد! يمكّنك Aspose.Words for .NET من تحديد محاذاة القاعدة الأفقية باستخدام خاصية Alignment. يمكنك الاختيار من بين خيارات متنوعة مثل Center وLeft وRight وJustified.

#### س: هل يمكنني تطبيق التظليل أو لون الخلفية على القاعدة الأفقية؟

ج: نعم، يمكنك إضافة تظليل أو لون الخلفية إلى القاعدة الأفقية. افتراضيًا، يتم تعيين الخاصية NoShade إلى true، ولكن يمكنك تعيينها إلى false وتحديد التظليل باستخدام الطرق المناسبة.

#### س: هل يمكنني إدراج قواعد أفقية متعددة في مستند واحد؟

ج: بالتأكيد! يمكنك إدراج قواعد أفقية متعددة في مستند Word باستخدام Aspose.Words لـ .NET. ما عليك سوى تكرار الخطوات الموجودة في البرنامج التعليمي حسب الحاجة لإضافة أي عدد تريده من القواعد الأفقية.