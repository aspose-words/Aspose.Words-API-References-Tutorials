---
title: تطبيق نمط الفقرة في مستند Word
linktitle: تطبيق نمط الفقرة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تطبيق نمط الفقرة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-paragraph-style/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تطبيق نمط الفقرة باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق نمط الفقرة.

## الخطوة 1: إنشاء وتكوين المستند

للبدء، قم بإنشاء مستند جديد وكائن DocumentBuilder مرتبط. إليك الطريقة:

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

## الخطوة 3: إضافة المحتوى

سنقوم بإضافة محتوى إلى الفقرة. إليك الطريقة:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### مثال على التعليمات البرمجية المصدر لتطبيق نمط الفقرة باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة تطبيق نمط الفقرة باستخدام Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

باستخدام هذا الرمز، ستتمكن من تطبيق نمط الفقرة باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي، اكتشفنا كيفية تطبيق نمط الفقرة في مستند Word باستخدام Aspose.Words for .NET. من خلال تعيين`StyleIdentifier` ملكية`ParagraphFormat`، تمكنا من تطبيق نمط مدمج على الفقرة. يوفر Aspose.Words for .NET نطاقًا واسعًا من خيارات التنسيق، بما في ذلك القدرة على إنشاء وتطبيق أنماط مخصصة، مما يتيح لك الحصول على مستندات ذات مظهر احترافي بسهولة.

### الأسئلة الشائعة

#### س: كيف يمكنني تطبيق نمط فقرة في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لتطبيق نمط فقرة في مستند Word باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:
1.  إنشاء مستند جديد و`DocumentBuilder` هدف.
2.  قم بتكوين نمط الفقرة عن طريق تعيين`StyleIdentifier` ملكية`ParagraphFormat` إلى معرف النمط المطلوب (على سبيل المثال،`StyleIdentifier.Title`, `StyleIdentifier.Heading1`، إلخ.).
3.  أضف محتوى إلى الفقرة باستخدام`Write` طريقة`DocumentBuilder`.
4.  احفظ المستند باستخدام`Save` طريقة.

#### س: ما هي معرفات الأنماط في Aspose.Words لـ .NET؟

 ج: معرفات الأنماط في Aspose.Words لـ .NET هي ثوابت محددة مسبقًا تمثل أنماط الفقرة المضمنة. يتوافق كل معرف نمط مع نمط معين مثل "العنوان" و"العنوان 1" و"العنوان 2" وما إلى ذلك.`StyleIdentifier` ملكية`ParagraphFormat`، يمكنك تطبيق النمط المطابق على الفقرة.

#### س: هل يمكنني إنشاء وتطبيق أنماط فقرات مخصصة باستخدام Aspose.Words لـ .NET؟

ج: نعم، باستخدام Aspose.Words لـ .NET، يمكنك إنشاء أنماط فقرات مخصصة وتطبيقها. يمكنك تحديد الأنماط الخاصة بك باستخدام خصائص تنسيق محددة مثل الخط والمحاذاة والمسافات البادئة وما إلى ذلك، وتطبيقها على الفقرات في المستند. يتيح لك هذا تحقيق تنسيق متسق ومخصص في جميع أنحاء المستند.