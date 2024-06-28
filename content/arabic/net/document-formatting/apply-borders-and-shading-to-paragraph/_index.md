---
title: تطبيق الحدود والتظليل على الفقرة في مستند Word
linktitle: تطبيق الحدود والتظليل على الفقرة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
سنوضح لك في هذا البرنامج التعليمي كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام وظيفة Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق تغييرات التنسيق.

## الخطوة 1: إنشاء وتكوين المستند

للبدء، قم بإنشاء مستند جديد وكائن DocumentBuilder مرتبط. إليك الطريقة:

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

## الخطوة 3: ملء الإعداد

سنقوم الآن بتكوين تعبئة الفقرة عن طريق تحديد الملمس وألوان التعبئة. إليك الطريقة:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## الخطوة 4: إضافة المحتوى

سنقوم بإضافة بعض المحتوى المنسق إلى الفقرة. إليك الطريقة:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### مثال على التعليمات البرمجية المصدر لتطبيق الحدود والتظليل على الفقرة باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة تطبيق الحدود والتظليل على الفقرة باستخدام Aspose.Words لـ .NET:

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

 في هذا البرنامج التعليمي، تعلمنا كيفية تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET. من خلال تكوين الفقرة`Borders` و`Shading` الخصائص، تمكنا من تعيين نمط الحدود ولون الخط ولون التعبئة للفقرة. يوفر Aspose.Words for .NET إمكانيات تنسيق قوية لتخصيص مظهر الفقرات وتحسين التمثيل المرئي لمستنداتك.

### الأسئلة الشائعة

#### س: كيف يمكنني تطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتطبيق الحدود والتظليل على فقرة في مستند Word باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:
1.  إنشاء مستند جديد و`DocumentBuilder` هدف.
2.  قم بتكوين حدود الفقرة عن طريق الوصول إلى`Borders` ملكية`ParagraphFormat` وتحديد نمط الحدود لكل جانب.
3. قم بتكوين تعبئة الفقرة عن طريق الوصول إلى`Shading` ملكية`ParagraphFormat` وتحديد الملمس وألوان التعبئة.
4.  أضف محتوى إلى الفقرة باستخدام`Write` طريقة`DocumentBuilder`.
5.  احفظ المستند باستخدام`Save` طريقة.

#### س: كيف أقوم بتعيين نمط الحدود لكل جانب من الفقرة؟

 ج: لتعيين نمط الحدود لكل جانب من جوانب الفقرة، يمكنك الوصول إلى`Borders` ملكية`ParagraphFormat` وتعيين`LineStyle` الملكية لكل`BorderType` (على سبيل المثال،`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). يمكنك تحديد أنماط خطوط مختلفة مثل`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`، إلخ.

#### س: كيف يمكنني تحديد الملمس وألوان التعبئة لتظليل الفقرة؟

 ج: لتحديد الملمس وألوان التعبئة لتظليل الفقرة، يمكنك الوصول إلى`Shading` ملكية`ParagraphFormat` وتعيين`Texture` الخاصية إلى فهرس الملمس المطلوب (على سبيل المثال،`TextureIndex.TextureDiagonalCross` ). يمكنك أيضًا ضبط`BackgroundPatternColor` و`ForegroundPatternColor` خصائص الألوان المطلوبة باستخدام`System.Drawing.Color` فصل.