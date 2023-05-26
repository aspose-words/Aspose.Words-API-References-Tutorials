---
title: إنشاء إشارة مرجعية
linktitle: إنشاء إشارة مرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء إشارات مرجعية في مستند وتحديد مستويات معاينة الإشارات المرجعية في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/create-bookmark/
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