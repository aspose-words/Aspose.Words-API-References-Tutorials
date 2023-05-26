---
title: تنسيق القاعدة الأفقية
linktitle: تنسيق القاعدة الأفقية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تنسيق القواعد الأفقية في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/horizontal-rule-format/
---

في هذا المثال الشامل ، ستتعلم كيفية تنسيق قاعدة أفقية في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستكون قادرًا على تخصيص المحاذاة والعرض والارتفاع واللون والخصائص الأخرى للقاعدة الأفقية.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء DocumentBuilder وإدراج قاعدة أفقية
للبدء ، أنشئ كائن DocumentBuilder واستخدم طريقة InsertHorizontalRule لإدراج قاعدة أفقية:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## الخطوة 2: الوصول إلى تنسيق القاعدة الأفقية
بعد ذلك ، قم بالوصول إلى الخاصية HorizontalRuleFormat لكائن الشكل لاسترداد خيارات التنسيق:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## الخطوة 3: تخصيص خيارات التنسيق
الآن ، يمكنك تخصيص خيارات تنسيق متنوعة للقاعدة الأفقية. على سبيل المثال ، يمكنك ضبط المحاذاة والعرض والارتفاع واللون والتظليل:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## الخطوة 4: احفظ المستند
بعد تنسيق القاعدة الأفقية ، احفظ المستند في ملف باستخدام طريقة Save للكائن Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### مثال على كود المصدر لتنسيق القاعدة الأفقية باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لتنسيق قاعدة أفقية باستخدام Aspose.Words for .NET:

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

تذكر أن تقوم بتعديل الكود وفقًا لمتطلباتك الخاصة وتعزيزه بوظائف إضافية حسب الحاجة.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تنسيق قاعدة أفقية في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن تخصيص مظهر القواعد الأفقية لتحسين التخطيط المرئي للمستند.

جرب خيارات تنسيق مختلفة لتحقيق النمط والتأثير المرغوب فيه للقواعد الأفقية.
