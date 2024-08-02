---
title: إظهار المراجعات في البالونات
linktitle: إظهار المراجعات في البالونات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: إظهار المراجعات في بالونات باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/show-revisions-in-balloons/
---

في هذا الدليل خطوة بخطوة، سنوضح لك كيفية إظهار المراجعات في بالونات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: تكوين خيارات عرض المراجعة

سنقوم بتكوين خيارات العرض لجعل المراجعات مرئية في البالونات.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## الخطوة 3: احفظ المستند بتنسيق PDF

وأخيرًا، سنقوم بحفظ المستند كملف PDF مع المراجعات المعروضة في البالونات.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## تنسيقات إخراج تخفيض السعر

يمكن تنسيق الإخراج في تخفيض السعر لتحسين إمكانية القراءة. على سبيل المثال :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### مثال على التعليمات البرمجية المصدر لعرض المراجعات في البالونات باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لإظهار المراجعات في البالونات في مستند باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// يقوم العرض بإدراج المراجعات في السطر، وحذف المراجعات وتنسيقها في البالونات.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// يعرض أشرطة المراجعة على الجانب الأيمن من الصفحة.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية عرض المراجعات في بالونات في مستند Word باستخدام Aspose.Words for .NET. باستخدام خيارات العرض المناسبة، تمكنا من جعل المراجعات مرئية في فقاعات مع أشرطة المراجعة على الجانب الأيمن. يوفر Aspose.Words for .NET العديد من الميزات القوية لمعالجة مستندات Word، بما في ذلك إدارة المراجعة. يمكنك الآن استخدام هذه المعرفة لإظهار المراجعات في بالونات في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.


### الأسئلة الشائعة

#### س: كيفية تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يتم عرض المراجعات في بالونات باستخدام Aspose.Words لـ .NET؟

 ج: استخدم`ShowInBalloons` ملكية`RevisionOptions` كائن لتكوين عرض المراجعات في البالونات. يمكنك ضبط هذه الخاصية على`ShowInBalloons.FormatAndDelete` لإظهار المراجعات في البالونات مع مراجعات الحذف والتنسيق.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### س: كيف يمكن حفظ مستند بتنسيق PDF باستخدام Aspose.Words لـ .NET؟

 ج: استخدم`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF. يجب عليك تحديد مسار الوجهة الكامل بامتداد ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```