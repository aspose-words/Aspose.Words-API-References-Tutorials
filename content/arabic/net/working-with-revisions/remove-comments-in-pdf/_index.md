---
title: إزالة التعليقات في ملف PDF
linktitle: إزالة التعليقات في ملف PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: قم بإزالة التعليقات في ملف PDF باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/remove-comments-in-pdf/
---

في هذا الدليل التفصيلي، سنخبرك بكيفية إزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على التعليقات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: إخفاء التعليقات في PDF

سنقوم بتكوين خيار التخطيط لإخفاء التعليقات عند إنشاء ملف PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## الخطوة 3: احفظ المستند كملف PDF

وأخيرًا، سنقوم بحفظ المستند بتنسيق PDF عن طريق حذف التعليقات.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## تنسيقات إخراج تخفيض السعر

يمكن تنسيق الإخراج في تخفيض السعر لتحسين إمكانية القراءة. على سبيل المثال :

```markdown
- Comments are hidden in the generated PDF.
```

### مثال على التعليمات البرمجية المصدر لإزالة التعليقات في ملف Pdf باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لإزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// إخفاء التعليقات في ملف PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إزالة التعليقات من ملف PDF باستخدام Aspose.Words for .NET. باستخدام خيارات التخطيط المناسبة، تمكنا من إخفاء التعليقات عند إنشاء ملف PDF. يوفر Aspose.Words for .NET مرونة كبيرة في التعامل مع ملفات Word وتحويلها إلى تنسيقات مختلفة، بما في ذلك PDF. يمكنك الآن تطبيق هذه المعرفة لإزالة التعليقات في ملفات PDF الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة لإزالة التعليقات في ملف pdf

#### س: كيفية تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكن إخفاء التعليقات في ملف PDF الذي تم إنشاؤه باستخدام Aspose.Words لـ .NET؟

 ج: استخدم`CommentDisplayMode` ملكية`LayoutOptions` كائن لتكوين كيفية عرض التعليقات عند إنشاء ملف PDF. لإخفاء التعليقات، قم بتعيين هذه الخاصية على`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### س: كيف يمكن حفظ المستند بصيغة PDF باستخدام Aspose.Words لـ .NET؟

 ج: استخدم`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF. حدد المسار الكامل لملف PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```