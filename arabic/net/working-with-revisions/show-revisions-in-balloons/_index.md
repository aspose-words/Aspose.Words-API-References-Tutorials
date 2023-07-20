---
title: إظهار المراجعات في بالونات
linktitle: إظهار المراجعات في بالونات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: اعرض المراجعات في بالونات باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/show-revisions-in-balloons/
---

في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية إظهار المراجعات في البالونات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تكوين خيارات عرض المراجعة

سنقوم بتهيئة خيارات العرض لجعل المراجعات مرئية في البالونات.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## الخطوة 3: احفظ المستند بتنسيق PDF

أخيرًا ، سنقوم بحفظ المستند كملف PDF مع إظهار المراجعات في بالونات.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## تنسيقات إخراج Markdown

يمكن تنسيق الإخراج في تخفيض السعر لتحسين إمكانية القراءة. على سبيل المثال :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### مثال على شفرة المصدر لـ Show Revisions In Balloons باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لإظهار المراجعات في البالونات في مستند باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// يجعل إدراج المراجعات مضمنة ، وحذف المراجعات وتنسيقها في البالونات.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// يعرض أشرطة المراجعة على الجانب الأيمن من الصفحة.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية عرض المراجعات في بالونات في مستند Word باستخدام Aspose.Words for .NET. باستخدام خيارات العرض المناسبة ، تمكنا من جعل المراجعات مرئية في فقاعات مع وجود أشرطة المراجعة على الجانب الأيمن. يوفر Aspose.Words for .NET العديد من الميزات القوية لمعالجة مستندات Word ، بما في ذلك إدارة المراجعة. يمكنك الآن استخدام هذه المعرفة لإظهار المراجعات في البالونات في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكن تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم ملف`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يتم عرض المراجعات في البالونات باستخدام Aspose.Words for .NET؟

 ج: استخدم ملف`ShowInBalloons` ممتلكات`RevisionOptions` كائن لتكوين عرض المراجعات في البالونات. يمكنك ضبط هذه الخاصية على`ShowInBalloons.FormatAndDelete` لإظهار المراجعات في البالونات مع تنقيحات الحذف والتنسيق.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### س: كيف تحفظ مستندًا بتنسيق PDF باستخدام Aspose.Words for .NET؟

 ج: استخدم ملف`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF. يجب تحديد مسار الوجهة الكامل بامتداد ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```