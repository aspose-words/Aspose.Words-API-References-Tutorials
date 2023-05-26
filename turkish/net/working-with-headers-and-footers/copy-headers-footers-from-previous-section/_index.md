---
title: نسخ تذييلات الرؤوس من القسم السابق
linktitle: نسخ تذييلات الرؤوس من القسم السابق
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية نسخ الرؤوس والتذييلات من القسم السابق في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية نسخ الرؤوس والتذييلات من القسم السابق في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: الوصول إلى القسم السابق

 أولاً ، قم باسترداد القسم السابق من خلال الوصول إلى ملف`PreviousSibling` خاصية القسم الحالي:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## الخطوة 2: التحقق من القسم السابق

بعد ذلك ، تحقق من وجود قسم سابق. إذا لم يكن هناك قسم سابق ، فنعود ببساطة:

```csharp
if (previousSection == null)
    return;
```

## الخطوة 3: مسح ونسخ الرؤوس والتذييلات

لنسخ الرؤوس والتذييلات من القسم السابق إلى القسم الحالي ، نقوم بمسح الرؤوس والتذييلات الموجودة في القسم الحالي ثم نكررها من خلال الرؤوس والتذييلات في القسم السابق لإضافة نسخ مستنسخة إلى القسم الحالي:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## الخطوة 4: حفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save("OutputDocument.docx");
```

هذا كل شيء! لقد نجحت في نسخ الرؤوس والتذييلات من القسم السابق إلى القسم الحالي في مستند Word باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لنسخ تذييلات الرؤوس من القسم السابق باستخدام Aspose.Words for .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.