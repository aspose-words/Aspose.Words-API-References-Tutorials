---
title: قم بتعيين خيارات التعليق الختامي
linktitle: قم بتعيين خيارات التعليق الختامي
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعيين خيارات التعليقات الختامية في مستندات Word باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /ar/net/working-with-footnote-and-endnote/set-endnote-options/
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

### التعليمات

#### س: كيف يمكنني تنسيق التعليقات الختامية في Aspose.Words؟

 ج: لتصميم التعليقات الختامية في Aspose.Words ، يمكنك استخدام`EndnoteOptions` الطبقة و`SeparatorNoteTextStyle` ملكية. يمكنك تحديد نمط الخط وحجمه ولونه وما إلى ذلك للتعليقات الختامية باستخدام هذه الخاصية.

#### س: هل من الممكن تخصيص ترقيم التعليقات الختامية في المستند؟

 ج: نعم ، من الممكن تخصيص ترقيم التعليقات الختامية في المستند. يمكنك استخدام ال`RestartRule` و`NumberStyle` خصائص`EndnoteOptions` فئة لتحديد قواعد إعادة التشغيل وأنماط الترقيم المحددة.

#### س: كيف يمكنني وضع التعليقات الختامية في مستند؟

 ج: لوضع التعليقات الختامية في مستند ما ، يمكنك استخدام الامتداد`Position`ممتلكات`EndnoteOptions` فصل. يمكنك تحديد ما إذا كان يجب وضع التعليقات الختامية في أسفل كل صفحة أو في نهاية كل قسم أو في نهاية المستند.

#### س: هل يمكنني تخصيص تنسيق ترقيم التعليقات الختامية؟

 ج: نعم ، يمكنك تخصيص تنسيق ترقيم التعليقات الختامية في Aspose.Words. استخدم ال`NumberFormat`ممتلكات`EndnoteOptions` فئة لتعيين التنسيق المطلوب ، مثل الأرقام العربية والأرقام الرومانية والحروف وما إلى ذلك.

#### س: هل من الممكن الاستمرار في ترقيم التعليقات الختامية بين أقسام المستند؟

 ج: نعم ، من الممكن الاستمرار في ترقيم التعليقات الختامية بين أقسام المستند. استخدم ال`RestartRule`ممتلكات`EndnoteOptions` فئة وضبطها على`RestartContinuous` للسماح باستمرار الترقيم بين الأقسام.