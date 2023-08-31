---
title: قم بتعيين خيارات التعليق الختامي
linktitle: قم بتعيين خيارات التعليق الختامي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين خيارات التعليقات الختامية في مستندات Word باستخدام Aspose.Words لـ .NET. البرنامج التعليمي خطوة بخطوة مع مثال التعليمات البرمجية المصدر.
type: docs
weight: 10
url: /ar/net/working-with-footnote-and-endnote/set-endnote-options/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية استخدام Aspose.Words لـ .NET لتعيين خيارات التعليقات الختامية في مستند Word. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وإعداده في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: تهيئة كائن المستند

 أولاً، قم بتهيئة`Document` كائن من خلال توفير المسار إلى المستند المصدر الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: تهيئة كائن DocumentBuilder

 بعد ذلك، قم بتهيئة`DocumentBuilder` كائن لتنفيذ العمليات على الوثيقة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة نص والتعليق الختامي

 استخدم ال`Write` طريقة`DocumentBuilder` كائن لإضافة نص إلى المستند، و`InsertFootnote` طريقة إدراج حاشية ختامية:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## الخطوة 4: تحديد خيارات التعليق الختامي

 الوصول إلى`EndnoteOptions` خاصية المستند لتعديل خيارات التعليق الختامي. في هذا المثال، قمنا بتعيين قاعدة إعادة التشغيل لإعادة التشغيل في كل صفحة والموضع حتى نهاية القسم:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## الخطوة 5: حفظ المستند

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

هذا كل شيء! لقد قمت بنجاح بتعيين خيارات التعليق الختامي في مستند Word باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لتعيين خيارات التعليق الختامي باستخدام Aspose.Words لـ .NET

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

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني تصميم التعليقات الختامية في Aspose.Words؟

 ج: لتصميم التعليقات الختامية في Aspose.Words، يمكنك استخدام`EndnoteOptions` الطبقة و`SeparatorNoteTextStyle` ملكية. يمكنك تحديد نمط الخط وحجمه ولونه وما إلى ذلك للتعليقات الختامية باستخدام هذه الخاصية.

#### س: هل من الممكن تخصيص ترقيم الحواشي الختامية في المستند؟

 ج: نعم، من الممكن تخصيص ترقيم الحواشي الختامية في المستند. يمكنك استخدام ال`RestartRule` و`NumberStyle` خصائص`EndnoteOptions` فئة لتحديد قواعد إعادة التشغيل المحددة وأنماط الترقيم.

#### س: كيف يمكنني وضع التعليقات الختامية في المستند؟

 ج: لوضع التعليقات الختامية في المستند، يمكنك استخدام`Position` ملكية`EndnoteOptions` فصل. يمكنك تحديد ما إذا كان يجب وضع التعليقات الختامية في أسفل كل صفحة، أو في نهاية كل قسم، أو في نهاية المستند.

#### س: هل يمكنني تخصيص تنسيق ترقيم التعليقات الختامية؟

 ج: نعم، يمكنك تخصيص تنسيق ترقيم التعليقات الختامية في Aspose.Words. استخدم ال`NumberFormat` ملكية`EndnoteOptions` فئة لتعيين التنسيق المطلوب، مثل الأرقام العربية والأرقام الرومانية والحروف، وما إلى ذلك.

#### س: هل من الممكن الاستمرار في ترقيم التعليقات الختامية بين أقسام المستند؟

 ج: نعم، من الممكن الاستمرار في ترقيم الحواشي الختامية بين أقسام المستند. استخدم ال`RestartRule` ملكية`EndnoteOptions` الصف وتعيينه على`RestartContinuous` للسماح بمواصلة الترقيم بين الأقسام.