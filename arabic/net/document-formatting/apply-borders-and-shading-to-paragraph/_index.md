---
title: تطبيق الحدود والتظليل على الفقرة
linktitle: تطبيق الحدود والتظليل على الفقرة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تطبيق الحدود والتظليل على فقرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية تطبيق الحدود والتظليل على فقرة باستخدام وظيفة Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر وتطبيق تغييرات التنسيق.

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
