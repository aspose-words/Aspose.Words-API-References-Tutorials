---
title: إنشاء تذييل الرأس
linktitle: إنشاء تذييل الرأس
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة الرؤوس والتذييلات وتخصيصها في مستندات Word باستخدام Aspose.Words for .NET. يضمن هذا الدليل خطوة بخطوة تنسيقًا احترافيًا للمستندات.
type: docs
weight: 10
url: /ar/net/working-with-headers-and-footers/create-header-footer/
---
## مقدمة

يمكن أن تؤدي إضافة الرؤوس والتذييلات إلى مستنداتك إلى تحسين احترافيتها وسهولة قراءتها. باستخدام Aspose.Words for .NET، يمكنك بسهولة إنشاء وتخصيص الرؤوس والتذييلات لمستندات Word الخاصة بك. في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة، مما يضمن أنه يمكنك تنفيذ هذه الميزات بسلاسة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

-  Aspose.Words لـ .NET: قم بالتنزيل والتثبيت من[رابط التحميل](https://releases.aspose.com/words/net/).
- بيئة التطوير: مثل Visual Studio، لكتابة وتشغيل التعليمات البرمجية الخاصة بك.
- المعرفة الأساسية بـ C#: فهم C# و.NET Framework.
- نموذج مستند: نموذج مستند لتطبيق الرؤوس والتذييلات، أو إنشاء مستند جديد كما هو موضح في البرنامج التعليمي.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى فئات وأساليب Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## الخطوة 1: تحديد دليل المستندات

حدد الدليل الذي سيتم حفظ المستند فيه. وهذا يساعد في إدارة المسار بفعالية.

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## الخطوة 2: إنشاء مستند جديد

 إنشاء مستند جديد و`DocumentBuilder`لتسهيل إضافة المحتوى.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: تكوين إعداد الصفحة

قم بإعداد إعدادات الصفحة، بما في ذلك ما إذا كانت الصفحة الأولى ستحتوي على رأس/تذييل مختلف.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## الخطوة 4: إضافة رأس إلى الصفحة الأولى

انتقل إلى قسم الرأس للصفحة الأولى وقم بتكوين نص الرأس.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## الخطوة 5: إضافة رأس أساسي

انتقل إلى قسم الرأس الأساسي وأدخل صورة ونصًا.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// أدخل صورة في الرأس
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## الخطوة 6: إضافة تذييل أساسي

انتقل إلى قسم التذييل الأساسي وقم بإنشاء جدول لتنسيق محتوى التذييل.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// إضافة ترقيم الصفحات
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## الخطوة 7: إضافة المحتوى وفواصل الصفحات

انتقل إلى نهاية المستند، وأضف فاصل صفحات، وأنشئ قسمًا جديدًا بإعدادات صفحة مختلفة.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## الخطوة 8: انسخ الرؤوس والتذييلات من القسم السابق

إذا كنت تريد إعادة استخدام الرؤوس والتذييلات من قسم سابق، فانسخها وقم بتطبيق التعديلات اللازمة.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## خاتمة

باتباع هذه الخطوات، يمكنك إضافة الرؤوس والتذييلات وتخصيصها بشكل فعال في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET. يؤدي ذلك إلى تحسين مظهر مستندك واحترافيته، مما يجعله أكثر قابلية للقراءة وجاذبية.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟

Aspose.Words for .NET هي مكتبة تمكن المطورين من إنشاء مستندات Word وتحريرها وتحويلها برمجيًا ضمن تطبيقات .NET.

### هل يمكنني إضافة صور إلى الرأس أو التذييل؟

 نعم، يمكنك بسهولة إضافة صور إلى الرأس أو التذييل باستخدام`DocumentBuilder.InsertImage` طريقة.

### كيف أقوم بتعيين رؤوس وتذييلات مختلفة للصفحة الأولى؟

 يمكنك تعيين رؤوس وتذييلات مختلفة للصفحة الأولى باستخدام`DifferentFirstPageHeaderFooter` ملكية`PageSetup` فصل.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Words؟

 يمكنك العثور على وثائق شاملة عن[صفحة وثائق Aspose.Words API](https://reference.aspose.com/words/net/).

### هل هناك دعم متاح لـ Aspose.Words؟

 نعم، Aspose يقدم الدعم من خلال[منتدى الدعم](https://forum.aspose.com/c/words/8).
