---
title: إنشاء إشارة مرجعية في مستند Word
linktitle: إنشاء إشارة مرجعية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء إشارات مرجعية في مستند Word وتحديد مستويات معاينة الإشارات المرجعية في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/create-bookmark/
---

في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة إنشاء إشارة مرجعية في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إنشاء إشارات مرجعية في مستند وتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء المستند والمولد

 قبل إنشاء الإشارات المرجعية، نحتاج إلى إنشاء مستند ومنشئ المستندات باستخدام الملف`Document` و`DocumentBuilder` أشياء:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إنشاء الإشارة المرجعية الرئيسية

 نحن نستخدم ال`StartBookmark` طريقة لبدء الإشارة المرجعية الرئيسية و`EndBookmark` طريقة لإنهاء ذلك. وفي المنتصف، يمكننا إضافة نص وإشارات مرجعية أخرى:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// أضف المزيد من الإشارات المرجعية أو النص هنا.

builder. EndBookmark("My Bookmark");
```

## الخطوة 3: إنشاء الإشارات المرجعية المتداخلة

يمكننا أيضًا إنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية. نحن نستخدم نفس الشيء`StartBookmark` و`EndBookmark` طرق إنشاء الإشارات المرجعية المتداخلة وإنهائها:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## الخطوة 4: تحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج

 نحن نستخدم ال`PdfSaveOptions` كائن لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج. نحن نستخدم ال`BookmarksOutlineLevels` ملكية

  لإضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة مع مستوياتها الخاصة:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### مثال على التعليمات البرمجية المصدر لإنشاء إشارة مرجعية باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح كيفية إنشاء الإشارات المرجعية باستخدام Aspose.Words لـ .NET:

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

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة إنشاء إشارة مرجعية في Aspose.Words لـ .NET. لقد اتبعنا دليلًا خطوة بخطوة لإنشاء إشارات مرجعية في مستند وتحديد مستويات معاينة الإشارات المرجعية في ملف PDF الناتج.

### الأسئلة الشائعة

#### س: ما هي المتطلبات الأساسية لاستخدام وظيفة "إنشاء إشارات مرجعية" في Aspose.Words لـ .NET؟

ج: لاستخدام وظيفة "إنشاء إشارات مرجعية" في Aspose.Words لـ .NET، يجب أن تكون لديك المعرفة الأساسية بلغة C#. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيفية إنشاء مستند في Aspose.Words لـ .NET؟

 ج: لإنشاء مستند في Aspose.Words لـ .NET، يمكنك استخدام`Document` فصل. هنا نموذج التعليمات البرمجية:

```csharp
Document doc = new Document();
```

#### س: كيف يمكن إنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words لـ .NET، يمكنك استخدام`StartBookmark` لبدء الإشارة المرجعية، قم بإضافة نص أو إشارات مرجعية أخرى بالداخل، ثم استخدم` EndBookmark` لإنهاء ذلك. هنا نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### س: كيف يمكن إنشاء إشارة مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارة مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words لـ .NET، يمكنك استخدام نفس الإشارة`StartBookmark` و`EndBookmark` طرق لبدء وإنهاء الإشارة المرجعية المتداخلة. هنا نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### س: كيفية تحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET؟

 ج: لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words لـ .NET، يمكنك استخدام`PdfSaveOptions` الطبقة و`BookmarksOutlineLevels` ملكية. يمكنك إضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة بمستوياتها الخاصة. هنا نموذج التعليمات البرمجية:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### س: كيف يمكن حفظ مستند بعد إنشاء الإشارات المرجعية باستخدام Aspose.Words لـ .NET؟

 ج: لحفظ مستند بعد إنشاء الإشارات المرجعية باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Save` طريقة`Document` كائن يحدد مسار الملف الوجهة. هنا نموذج التعليمات البرمجية:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### س: كيفية تحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words for .NET؟

 ج: لتحديد مستويات معاينة الإشارة المرجعية في ملف PDF الناتج باستخدام Aspose.Words لـ .NET، يمكنك استخدام`PdfSaveOptions` الطبقة و`BookmarksOutlineLevels` ملكية. يمكنك إضافة إشارات مرجعية رئيسية وإشارات مرجعية متداخلة بمستوياتها الخاصة. هنا نموذج التعليمات البرمجية:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### س: كيف يمكن إنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارات مرجعية متداخلة داخل إشارة مرجعية رئيسية باستخدام Aspose.Words لـ .NET، يمكنك استخدام نفس الشيء`StartBookmark` و`EndBookmark` طرق لبدء وإنهاء الإشارات المرجعية المتداخلة. تأكد من تحديد الإشارة المرجعية الأصلية كمعلمة عند الاتصال بـ`StartBookmark` طريقة. هنا نموذج التعليمات البرمجية:

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

#### س: كيفية إضافة نص داخل إشارة مرجعية باستخدام Aspose.Words لـ .NET؟

 ج: لإضافة نص داخل إشارة مرجعية باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Write` طريقة`DocumentBuilder`كائن يحدد النص المراد إضافته. هنا نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### س: كيف يمكن إنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء إشارة مرجعية رئيسية في مستند باستخدام Aspose.Words لـ .NET، يمكنك استخدام`StartBookmark` طريقة لبدء الإشارة المرجعية و`EndBookmark` طريقة لإنهاء ذلك. هنا نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```