---
title: تعيين موضع الحاشية السفلية وملاحظة النهاية
linktitle: تعيين موضع الحاشية السفلية وملاحظة النهاية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين موضع الحواشي السفلية والتعليقات الختامية في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتعيين موضع الحواشي السفلية والتعليقات الختامية في مستند Word. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` من خلال توفير المسار إلى المستند المصدر:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: تحديد موضع الحاشية السفلية والتعليق الختامي

 بعد ذلك ، قم بالوصول إلى`FootnoteOptions` و`EndnoteOptions`خصائص المستند لتعيين موضع الحواشي السفلية والتعليقات الختامية. في هذا المثال ، قمنا بتعيين موضع الحواشي السفلية ليكون أسفل النص وموضع التعليقات الختامية في نهاية القسم:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## الخطوة 3: حفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

هذا كل شيء! لقد نجحت في تعيين موضع الحواشي السفلية والتعليقات الختامية في مستند Word باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Set Footnote And Endnote Position باستخدام Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.
