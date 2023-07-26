---
title: مجموعة فواصل أسطر الطباعة الآسيوية في مستند Word
linktitle: مجموعة فواصل أسطر الطباعة الآسيوية في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام مجموعة فواصل أسطر الطباعة الآسيوية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/asian-typography-line-break-group/
---
في هذا البرنامج التعليمي ، سوف نوضح لك كيفية استخدام مجموعة فواصل أسطر الطباعة الآسيوية في ميزة مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر وتطبيق تغييرات التنسيق.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الذي يحتوي على الطباعة الآسيوية في كائن المستند. إليك الطريقة:

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

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### مثال على شفرة المصدر لمجموعة خطوط الطباعة الآسيوية باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة Asian Typography Line Break Group مع Aspose.Words for .NET:

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
باستخدام هذا الرمز ، ستتمكن من تطبيق مجموعة فواصل أسطر الطباعة الآسيوية باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي ، استكشفنا ميزة "Asian Typography Line Break Group" في Aspose.Words for .NET. من خلال تكوين ملف`FarEastLineBreakControl`, `WordWrap` ، و`HangingPunctuation` خصائص`ParagraphFormat`، تمكنا من التحكم في سلوك كسر الأسطر للطباعة الآسيوية في مستند Word. هذه الميزة مفيدة للتعامل مع الأحرف الآسيوية والتأكد من فواصل الأسطر وتغليف الكلمات في المستندات ذات المحتوى المختلط بلغات مختلفة.

### التعليمات

#### س: ما هي ميزة "Asian Typography Line Break Group" في Aspose.Words for .NET؟

ج: تسمح لك ميزة "Asian Typography Line Break Group" في Aspose.Words for .NET بالتحكم في سلوك فصل الأسطر للطباعة الآسيوية في مستند Word. على وجه التحديد ، فإنه يؤثر على كيفية كسر الأسطر ولفها عند التعامل مع الأحرف الآسيوية في الفقرات.

#### س: كيف يمكنني تمكين "Asian Typography Line Break Group" في Aspose.Words for .NET؟

 ج: لتمكين "Asian Typography Line Break Group" ، تحتاج إلى تكوين`FarEastLineBreakControl`, `WordWrap` ، و`HangingPunctuation` خصائص`ParagraphFormat` للفقرة (الفقرات) ذات الصلة في المستند الخاص بك. جلسة`FarEastLineBreakControl` ل`false` يضمن أن الأحرف الآسيوية يتم التعامل معها بشكل مشابه للأحرف اللاتينية فيما يتعلق بفصل الأسطر.`WordWrap` ضبط ل`true` يتيح التفاف الكلمات للطباعة الآسيوية ، و`HangingPunctuation` ضبط ل`false` يمنع تعليق الترقيم في النص الآسيوي.

#### س: هل يمكنني تطبيق "مجموعة فواصل أسطر الطباعة الآسيوية" على فقرات معينة في المستند؟

ج: نعم ، يمكنك تطبيق إعدادات "Asian Typography Line Break Group" على فقرات معينة في مستند Word. في رمز المثال ، يتم تطبيق الإعدادات على الفقرة الأولى من المستند. يمكنك ضبط الكود لاستهداف فقرات أخرى حسب الحاجة من خلال الوصول إليها من خلال ملف`Paragraphs` مجموعة من الأقسام ذات الصلة في الوثيقة.