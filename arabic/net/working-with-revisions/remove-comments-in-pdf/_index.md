---
title: إزالة التعليقات في ملف Pdf
linktitle: إزالة التعليقات في ملف Pdf
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: قم بإزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/remove-comments-in-pdf/
---

في هذا الدليل المفصل خطوة بخطوة ، سنخبرك بكيفية إزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على التعليقات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة الثانية: إخفاء التعليقات في ملف PDF

سنقوم بتكوين خيار التخطيط لإخفاء التعليقات عند إنشاء ملف PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## الخطوة 3: احفظ المستند كملف PDF

أخيرًا ، سنحفظ المستند بتنسيق PDF عن طريق حذف التعليقات.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## تنسيقات إخراج Markdown

يمكن تنسيق الإخراج في تخفيض السعر لتحسين إمكانية القراءة. على سبيل المثال :

```markdown
- Comments are hidden in the generated PDF.
```

### مثال على شفرة المصدر لـ Remove Comments In Pdf باستخدام Aspose.Words for .NET

إليك التعليمات البرمجية المصدر الكاملة لإزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// إخفاء التعليقات في PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إزالة التعليقات من ملف PDF باستخدام Aspose.Words for .NET. باستخدام خيارات التخطيط المناسبة ، تمكنا من إخفاء التعليقات عند إنشاء ملف PDF. يوفر Aspose.Words for .NET مرونة كبيرة في معالجة ملفات Word وتحويلها إلى تنسيقات مختلفة ، بما في ذلك PDF. يمكنك الآن تطبيق هذه المعرفة لإزالة التعليقات من ملفات PDF الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة لإزالة التعليقات في ملف pdf

#### س: كيف يمكن تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم ملف`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف تخفي التعليقات في ملف PDF الذي تم إنشاؤه باستخدام Aspose.Words for .NET؟

 ج: استخدم ملف`CommentDisplayMode`ممتلكات`LayoutOptions` لتكوين كيفية عرض التعليقات عند إنشاء ملف PDF. لإخفاء التعليقات ، اضبط هذه الخاصية على`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### س: كيف تحفظ المستند بصيغة PDF باستخدام Aspose.Words for .NET؟

 ج: استخدم ملف`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF. حدد المسار الكامل لملف PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```