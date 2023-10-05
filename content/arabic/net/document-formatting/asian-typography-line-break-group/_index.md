---
title: الطباعة الآسيوية مجموعة فاصل الأسطر في مستند Word
linktitle: الطباعة الآسيوية مجموعة فاصل الأسطر في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام مجموعة فواصل أسطر الطباعة الآسيوية في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/asian-typography-line-break-group/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية استخدام مجموعة فواصل أسطر الطباعة الآسيوية في ميزة مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق تغييرات التنسيق.

## الخطوة 1: تحميل الوثيقة

للبدء، حدد الدليل الخاص بمستنداتك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن Document. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## الخطوة 2: إعداد الطباعة الآسيوية

سنقوم الآن بتكوين إعدادات الطباعة الآسيوية للفقرة الأولى من المستند. إليك الطريقة:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### مثال على التعليمات البرمجية المصدر لمجموعة فاصل الأسطر للطباعة الآسيوية باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة مجموعة فاصل الأسطر للطباعة الآسيوية مع Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
باستخدام هذا الرمز، ستتمكن من تطبيق مجموعة فواصل أسطر الطباعة الآسيوية باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي، اكتشفنا ميزة "مجموعة فواصل الأسطر للطباعة الآسيوية" في Aspose.Words لـ .NET. من خلال تكوين`FarEastLineBreakControl`, `WordWrap` ، و`HangingPunctuation` خصائص`ParagraphFormat`، تمكنا من التحكم في سلوك كسر الأسطر للطباعة الآسيوية في مستند Word. تعد هذه الميزة مفيدة للتعامل مع الأحرف الآسيوية وضمان فواصل الأسطر المناسبة والتفاف الكلمات في المستندات ذات المحتوى اللغوي المختلط.

### الأسئلة الشائعة

#### س: ما هي ميزة "مجموعة فاصل الأسطر للطباعة الآسيوية" في Aspose.Words لـ .NET؟

ج: تسمح لك ميزة "مجموعة فاصل الأسطر للطباعة الآسيوية" في Aspose.Words لـ .NET بالتحكم في سلوك فصل الأسطر للطباعة الآسيوية في مستند Word. على وجه التحديد، فإنه يؤثر على كيفية تقسيم الأسطر والتفافها عند التعامل مع الأحرف الآسيوية في الفقرات.

#### س: كيف يمكنني تمكين "مجموعة فاصل أسطر الطباعة الآسيوية" في Aspose.Words لـ .NET؟

 ج: لتمكين "مجموعة فاصل أسطر الطباعة الآسيوية"، تحتاج إلى تكوين`FarEastLineBreakControl`, `WordWrap` ، و`HangingPunctuation` خصائص`ParagraphFormat` للفقرة (الفقرات) ذات الصلة في وثيقتك. جلسة`FarEastLineBreakControl` ل`false` يضمن أن يتم التعامل مع الأحرف الآسيوية بشكل مشابه للأحرف اللاتينية فيما يتعلق بفصل الأسطر.`WordWrap` ضبط ل`true` يتيح التفاف الكلمات للطباعة الآسيوية، و`HangingPunctuation` ضبط ل`false` يمنع علامات الترقيم من التعليق في النص الآسيوي.

#### س: هل يمكنني تطبيق "مجموعة فواصل الأسطر للطباعة الآسيوية" على فقرات معينة في المستند؟

ج: نعم، يمكنك تطبيق إعدادات "مجموعة فواصل الأسطر للطباعة الآسيوية" على فقرات معينة في مستند Word. في رمز المثال، يتم تطبيق الإعدادات على الفقرة الأولى من المستند. يمكنك ضبط الكود لاستهداف فقرات أخرى حسب الحاجة عن طريق الوصول إليها من خلال`Paragraphs` جمع القسم (الأقسام) ذات الصلة في الوثيقة.