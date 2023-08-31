---
title: قم بتطبيق نمط الفقرة في مستند Word
linktitle: قم بتطبيق نمط الفقرة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تطبيق نمط فقرة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-paragraph-style/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تطبيق نمط فقرة باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق نمط الفقرة.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين نمط الفقرة

سنقوم الآن بتكوين نمط الفقرة باستخدام معرف النمط المدمج. إليك الطريقة:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## الخطوة 3: أضف محتوى

سنقوم بإضافة محتوى إلى الفقرة. إليك الطريقة:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### مثال على شفرة المصدر لتطبيق Paragraph Style باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة "تطبيق نمط الفقرة" مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

باستخدام هذا الرمز ، ستتمكن من تطبيق نمط فقرة باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي ، اكتشفنا كيفية تطبيق نمط فقرة في مستند Word باستخدام Aspose.Words for .NET. عن طريق تحديد`StyleIdentifier` ممتلكات`ParagraphFormat`، تمكنا من تطبيق نمط مدمج على الفقرة. يوفر Aspose.Words for .NET نطاقًا واسعًا من خيارات التنسيق ، بما في ذلك القدرة على إنشاء أنماط مخصصة وتطبيقها ، مما يتيح لك الحصول على مستندات ذات مظهر احترافي بسهولة.

### التعليمات

#### س: كيف يمكنني تطبيق نمط فقرة في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتطبيق نمط فقرة في مستند Word باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:
1.  قم بإنشاء مستند جديد وملف`DocumentBuilder` هدف.
2.  تكوين نمط الفقرة عن طريق تعيين`StyleIdentifier` ممتلكات`ParagraphFormat` إلى معرف النمط المطلوب (على سبيل المثال ،`StyleIdentifier.Title`, `StyleIdentifier.Heading1`، إلخ.).
3.  أضف محتوى إلى الفقرة باستخدام`Write` طريقة`DocumentBuilder`.
4.  احفظ المستند باستخدام ملف`Save` طريقة.

#### س: ما هي معرفات الأنماط في Aspose.Words for .NET؟

 ج: معرفات النمط في Aspose.Words for .NET هي ثوابت محددة مسبقًا تمثل أنماط فقرة مضمنة. يتوافق كل معرّف نمط مع نمط معين مثل "العنوان" و "العنوان 1" و "العنوان 2" وما إلى ذلك. من خلال تعيين`StyleIdentifier` ممتلكات`ParagraphFormat`، يمكنك تطبيق النمط المقابل على الفقرة.

#### س: هل يمكنني إنشاء وتطبيق أنماط فقرة مخصصة باستخدام Aspose.Words for .NET؟

ج: نعم ، باستخدام Aspose.Words for .NET ، يمكنك إنشاء وتطبيق أنماط فقرة مخصصة. يمكنك تحديد الأنماط الخاصة بك بخصائص تنسيق معينة مثل الخط والمحاذاة والمسافة البادئة وما إلى ذلك ، وتطبيقها على الفقرات في المستند. يتيح لك ذلك تحقيق تنسيق متسق ومخصص في جميع أنحاء المستند.