---
title: الانتقال إلى تذييلات الرؤوس
linktitle: الانتقال إلى تذييلات الرؤوس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET للتنقل وتعديل الرؤوس والتذييلات في مستندات Word باستخدام هذا الدليل التفصيلي.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-headers-footers/
---

في هذا المثال ، سوف نستكشف ميزة Move To Headers Footers في Aspose.Words for .NET. Aspose.Words مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word وتعديلها وتحويلها برمجيًا. تتيح لنا ميزة Move To Headers / Footers التنقل إلى رؤوس وتذييلات مختلفة داخل المستند وإضافة محتوى إليها.

دعنا ننتقل إلى الكود المصدري خطوة بخطوة لفهم كيفية استخدام ميزة Move To Headers / Footers باستخدام Aspose.Words for .NET.



## الخطوة 1: تهيئة مستند إنشاء المستندات

أولاً ، قم بتهيئة كائنات Document و DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين الرؤوس والتذييلات

حدد إعدادات الرأس / التذييل للمستند. في هذا المثال ، قمنا بتعيين الرؤوس والتذييلات لتكون مختلفة للصفحة الأولى وللصفحات الفردية / الزوجية:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## الخطوة 3: إنشاء رؤوس الصفحات المختلفة

انتقل إلى كل نوع من أنواع العناوين وأضف محتوى إليها. في هذا المثال ، نقوم بإنشاء رؤوس للصفحة الأولى وحتى الصفحات وجميع الصفحات الأخرى:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## الخطوة 4: إنشاء صفحات في المستند
أضف محتوى إلى المستند لإنشاء صفحات متعددة. على سبيل المثال:

```csharp
// قم بإنشاء صفحتين في المستند.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## الخطوة 5: حفظ المستند

احفظ المستند المعدل في المكان المطلوب:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

تأكد من تحديد مسار الملف المناسب وتنسيقه (على سبيل المثال ، DOCX).

### مثال على شفرة المصدر لـ Move To Headers / Footers باستخدام Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// حدد أننا نريد اختلاف الرؤوس والتذييلات للصفحات الأولى والزوجية والفردية.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// قم بإنشاء الرؤوس.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// قم بإنشاء صفحتين في المستند.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```
