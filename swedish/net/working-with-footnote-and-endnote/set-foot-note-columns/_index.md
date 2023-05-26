---
title: تعيين أعمدة الملاحظات القدم
linktitle: تعيين أعمدة الملاحظات القدم
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين عدد الأعمدة للحواشي السفلية في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتعيين عدد الأعمدة للحواشي السفلية في مستند Word. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` من خلال توفير المسار إلى المستند المصدر:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: إعداد أعمدة الحواشي السفلية

 بعد ذلك ، قم بالوصول إلى`FootnoteOptions`خاصية المستند وتعيين`Columns` الخاصية لتحديد عدد أعمدة الحواشي السفلية. في هذا المثال ، قمنا بتعيينه على 3 أعمدة:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## الخطوة 3: حفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

هذا كل شيء! لقد نجحت في تعيين عدد الأعمدة للحواشي السفلية في مستند Word باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Set Footnote Columns باستخدام Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// حدد عدد الأعمدة التي يتم بها تنسيق منطقة الحواشي السفلية.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.