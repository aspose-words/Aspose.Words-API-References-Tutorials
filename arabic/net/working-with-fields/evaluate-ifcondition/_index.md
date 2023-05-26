---
title: تقييم حالة IF
linktitle: تقييم حالة IF
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتقييم حالة IF في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/evaluate-ifcondition/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "Evaluate IF Condition" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إنشاء منشئ المستندات

في الكود المقدم ، نبدأ بإنشاء منشئ المستندات.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: أدخل حقل IF

 نحن نستخدم ال`InsertField()` طريقة لإدراج حقل IF في المستند الذي يحدد الشرط المطلوب تقييمه.

```csharp
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);
```

استخدمنا هنا الشرط "1 = 1" كمثال ، ولكن يمكنك تخصيص الشرط حسب الحاجة.

## الخطوة 3: تقييم شرط IF

 ال`EvaluateCondition()`الطريقة المستخدمة لتقييم حالة حقل IF.

```csharp
FieldIfComparisonResult actualResult = field.EvaluateCondition();
```

 ال`actualResult` متغير يحتوي على نتيجة تقييم الحالة.

### نموذج التعليمات البرمجية المصدر لتقييم حالة IF باستخدام Aspose.Words for .NET

```csharp
// إنشاء منشئ الوثيقة.
DocumentBuilder builder = new DocumentBuilder();

// أدخل حقل IF في المستند.
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);

// قم بتقييم حالة IF.
FieldIfComparisonResult actualResult = field.EvaluateCondition();

// اعرض نتيجة التقييم.
Console.WriteLine(actualResult);
```

في هذا المثال ، أنشأنا منشئ مستندات ، وأدرجنا حقل IF بشرط محدد ، ثم قمنا بتقييم الشرط. ثم يتم عرض نتيجة التقييم في وحدة التحكم.

هذا يختتم دليلنا حول استخدام ميزة "تقييم حالة الحالة" مع Aspose.Words for .NET.
