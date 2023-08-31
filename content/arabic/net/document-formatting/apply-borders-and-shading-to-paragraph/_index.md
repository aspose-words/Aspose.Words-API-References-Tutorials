---
title: تطبيق الحدود والتظليل على فقرة في مستند Word
linktitle: تطبيق الحدود والتظليل على فقرة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
في هذا البرنامج التعليمي ، سوف نوضح لك كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام وظيفة Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر وتطبيق تغييرات التنسيق.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين الحدود

لنقم الآن بتكوين حدود الفقرة عن طريق تحديد نمط الحدود لكل جانب. إليك الطريقة:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## الخطوة 3: إعداد الملء

سنقوم الآن بتكوين تعبئة الفقرة عن طريق تحديد النسيج وألوان التعبئة. إليك الطريقة:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## الخطوة 4: أضف محتوى

سنقوم بإضافة بعض المحتوى المنسق إلى الفقرة. إليك الطريقة:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### مثال على الكود المصدري لتطبيق الحدود والتظليل على الفقرة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة "تطبيق الحدود والتظليل على الفقرة" باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET. عن طريق تكوين الفقرة`Borders` و`Shading` الخصائص ، تمكنا من ضبط نمط الحدود ولون الخط ولون التعبئة للفقرة. يوفر Aspose.Words for .NET إمكانيات تنسيق قوية لتخصيص مظهر الفقرات وتحسين التمثيل المرئي لمستنداتك.

### التعليمات

#### س: كيف يمكنني تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:
1.  قم بإنشاء مستند جديد وملف`DocumentBuilder` هدف.
2.  قم بتكوين حدود الفقرة بالوصول إلى ملف`Borders` ممتلكات`ParagraphFormat` وتعيين نمط الحدود لكل جانب.
3.  تكوين تعبئة الفقرة عن طريق الوصول إلى`Shading` ممتلكات`ParagraphFormat` وتحديد النسيج وملء الألوان.
4.  أضف محتوى إلى الفقرة باستخدام`Write` طريقة`DocumentBuilder`.
5.  احفظ المستند باستخدام ملف`Save` طريقة.

#### س: كيف يمكنني تعيين نمط الحد لكل جانب من جوانب الفقرة؟

 ج: لتعيين نمط الحد لكل جانب من جوانب الفقرة ، يمكنك الوصول إلى ملف`Borders` ممتلكات`ParagraphFormat` وضبط`LineStyle` الممتلكات لكل منها`BorderType` (على سبيل المثال ،`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). يمكنك تحديد أنماط خطوط مختلفة مثل`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`، إلخ.

#### س: كيف يمكنني تحديد ألوان النسيج والتعبئة لتظليل الفقرة؟

 ج: لتحديد ألوان النسيج والتعبئة لتظليل الفقرة ، يمكنك الوصول إلى تنسيق`Shading` ممتلكات`ParagraphFormat` وضبط`Texture` الخاصية إلى فهرس النسيج المطلوب (على سبيل المثال ،`TextureIndex.TextureDiagonalCross` ). يمكنك أيضًا ضبط ملف`BackgroundPatternColor` و`ForegroundPatternColor` خصائص الألوان المرغوبة باستخدام`System.Drawing.Color` فصل.