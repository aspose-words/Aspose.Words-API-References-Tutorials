---
title: قم بتعيين خيارات التعليق الختامي
linktitle: قم بتعيين خيارات التعليق الختامي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين خيارات التعليقات الختامية في مستندات Word باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-endnote-options/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتعيين خيارات التعليقات الختامية في مستند Word. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` من خلال توفير المسار إلى المستند المصدر:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: تهيئة كائن DocumentBuilder

 بعد ذلك ، قم بتهيئة ملف`DocumentBuilder` كائن لإجراء عمليات على المستند:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة نص وتعليق ختامي

 استخدم ال`Write` طريقة`DocumentBuilder` كائن لإضافة نص إلى المستند ، و`InsertFootnote` طريقة لإدراج تعليق ختامي:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## الخطوة 4: تعيين خيارات التعليقات الختامية

 الوصول إلى`EndnoteOptions` خاصية المستند لتعديل خيارات التعليقات الختامية. في هذا المثال ، قمنا بتعيين قاعدة إعادة التشغيل لإعادة التشغيل في كل صفحة والموضع إلى نهاية القسم:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## الخطوة 5: حفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

هذا كل شيء! لقد نجحت في تعيين خيارات التعليقات الختامية في مستند Word باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لتعيين خيارات التعليق الختامي باستخدام Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.
