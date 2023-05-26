---
title: إزالة التعليقات في ملف PDF
linktitle: إزالة التعليقات في ملف PDF
second_title: Aspose.Words لمراجع .NET API
description: قم بإزالة التعليقات في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/remove-comments-in-pdf/
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