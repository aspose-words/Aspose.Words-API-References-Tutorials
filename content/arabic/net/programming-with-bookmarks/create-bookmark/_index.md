---
title: إنشاء إشارة مرجعية في مستند Word
linktitle: إنشاء إشارة مرجعية في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء إشارات مرجعية في مستند Word وتحديد مستويات معاينة الإشارات المرجعية في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/create-bookmark/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة إنشاء إشارة مرجعية في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إنشاء إشارات مرجعية في مستند وتحديد مستويات معاينة الإشارات المرجعية في ملف PDF ناتج.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء المستند والمولد

 قبل إنشاء إشارات مرجعية ، نحتاج إلى إنشاء مستند ومنشئ مستندات باستخدام امتداد`Document` و`DocumentBuilder` أشياء:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إنشاء الإشارة المرجعية الرئيسية

 نحن نستخدم ال`StartBookmark` طريقة لبدء إشارة مرجعية رئيسية و`EndBookmark` طريقة لإنهائه. في ما بينهما ، يمكننا إضافة نص وإشارات مرجعية أخرى:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// أضف المزيد من الإشارات المرجعية أو النص هنا.

builder. EndBookmark("My Bookmark");
```

## الخطوة 3: إنشاء إشارات مرجعية متداخلة

 يمكننا أيضًا إنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية. نحن نستخدم نفس الشيء`StartBookmark` و`EndBookmark` طرق لإنشاء وإنهاء الإشارات المرجعية المتداخلة:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## الخطوة 4: تحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج

 نحن نستخدم ال`PdfSaveOptions` لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج. نحن نستخدم ال`BookmarksOutlineLevels` ملكية

  لإضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة بمستوياتها الخاصة:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### مثال على شفرة المصدر لإنشاء إشارة مرجعية باستخدام Aspose.Words for .NET

إليك المثال الكامل لشفرة المصدر لتوضيح إنشاء إشارات مرجعية باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة إنشاء إشارة مرجعية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء إشارات مرجعية في مستند وتحديد مستويات معاينة الإشارة المرجعية في ملف PDF ناتج.

### أسئلة وأجوبة

#### س: ما هي المتطلبات الأساسية لاستخدام وظيفة "إنشاء إشارات مرجعية" في Aspose.Words for .NET؟

ج: لاستخدام وظيفة "إنشاء إشارات مرجعية" في Aspose.Words for .NET ، يجب أن تكون لديك معرفة أساسية بلغة C #. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيف تنشئ مستندًا في Aspose.Words for .NET؟

 ج: لإنشاء مستند في Aspose.Words for .NET ، يمكنك استخدام`Document`فصل. إليك نموذج التعليمات البرمجية:

```csharp
Document doc = new Document();
```

#### س: كيفية إنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words for .NET ، يمكنك استخدام`StartBookmark` طريقة لبدء الإشارة المرجعية أو إضافة نص أو إشارات مرجعية أخرى بالداخل ، ثم استخدم ملف` EndBookmark` لإنهائه. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### س: كيفية إنشاء إشارة مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارة مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET ، يمكنك استخدام نفس الإشارة`StartBookmark` و`EndBookmark` طرق لبدء وإنهاء الإشارة المرجعية المتداخلة. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### س: كيف تحدد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET؟

 ج: لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET ، يمكنك استخدام`PdfSaveOptions` الطبقة و`BookmarksOutlineLevels` ملكية. يمكنك إضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة بمستوياتها الخاصة. إليك نموذج التعليمات البرمجية:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### س: كيف تحفظ مستندًا بعد إنشاء إشارات مرجعية باستخدام Aspose.Words for .NET؟

 ج: لحفظ مستند بعد إنشاء إشارات مرجعية باستخدام Aspose.Words for .NET ، يمكنك استخدام`Save` طريقة`Document` كائن يحدد مسار الملف الوجهة. إليك نموذج التعليمات البرمجية:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### س: كيف تحدد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET؟

 ج: لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET ، يمكنك استخدام`PdfSaveOptions` الطبقة و`BookmarksOutlineLevels` ملكية. يمكنك إضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة بمستوياتها الخاصة. إليك نموذج التعليمات البرمجية:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### س: كيفية إنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET ، يمكنك استخدام نفس الإشارات`StartBookmark` و`EndBookmark` طرق لبدء وإنهاء الإشارات المرجعية المتداخلة. تأكد من تحديد الإشارة المرجعية الأصلية كمعامل عند استدعاء ملف`StartBookmark` طريقة. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### س: كيف تضيف نصًا داخل إشارة مرجعية باستخدام Aspose.Words for .NET؟

 ج: لإضافة نص داخل إشارة مرجعية باستخدام Aspose.Words for .NET ، يمكنك استخدام`Write` طريقة`DocumentBuilder` كائن يحدد النص المراد إضافته. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### س: كيفية إنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words for .NET ، يمكنك استخدام`StartBookmark` طريقة لبدء الإشارة المرجعية و`EndBookmark` طريقة لإنهائه. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```