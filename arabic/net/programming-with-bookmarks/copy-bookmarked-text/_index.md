---
title: نسخ النص الذي تم وضع إشارة مرجعية عليه
linktitle: نسخ النص الذي تم وضع إشارة مرجعية عليه
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية نسخ نص إشارة مرجعية من مستند مصدر إلى مستند آخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/copy-bookmarked-text/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Copy Bookmarked Text في Aspose.Words for .NET library. تتيح لك هذه الميزة نسخ محتويات إشارة مرجعية معينة من مستند مصدر إلى مستند آخر.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل المستند المصدر

 قبل نسخ نص الإشارة المرجعية ، نحتاج إلى تحميل المستند المصدر في ملف`Document` كائن باستخدام مسار الملف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## الخطوة 2: الحصول على إشارة مرجعية المصدر

 نحن نستخدم ال`Bookmarks` خاصية نطاق المستند المصدر للحصول على الإشارة المرجعية المحددة التي نريد نسخها:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## الخطوة 3: إنشاء وثيقة الوجهة

نقوم بإنشاء مستند جديد سيكون بمثابة المستند الوجهة لنسخ محتوى الإشارة المرجعية:

```csharp
Document dstDoc = new Document();
```

## الخطوة 4: تحديد موقع النسخ

نحدد الموقع حيث نريد إضافة النص المنسوخ. في مثالنا ، نضيف النص إلى نهاية نص القسم الأخير من المستند الوجهة:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## الخطوة 5: استيراد نص الإشارة المرجعية ونسخه

 نحن نستخدم`NodeImporter`كائن لاستيراد نص إشارة مرجعية ونسخه من مستند مصدر إلى المستند الوجهة:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### مثال على شفرة المصدر لـ Copy Bookmarked Text باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح نسخ النص من إشارة مرجعية باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// هذه هي الإشارة المرجعية التي نريد نسخ محتواها.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// سنضيف إلى هذه الوثيقة.
	Document dstDoc = new Document();

	// لنفترض أننا سنلحق بنهاية نص القسم الأخير.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// إذا قمت بالاستيراد عدة مرات بدون سياق واحد ، فسيؤدي ذلك إلى إنشاء العديد من الأنماط.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام الوظيفة Copy Bookmarked Text من Aspose.Words for .NET. اتبعنا دليلًا تفصيليًا لنسخ محتويات إشارة مرجعية من مستند مصدر إلى مستند آخر.