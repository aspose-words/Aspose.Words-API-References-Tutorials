---
title: نسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
linktitle: نسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية نسخ نص الإشارة المرجعية في مستند Word إلى مستند آخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/copy-bookmarked-text/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Copy Bookmarked Text في Aspose.Words for .NET library. تتيح لك هذه الميزة نسخ محتويات إشارة مرجعية معينة من مستند مصدر إلى مستند آخر.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل مستند المصدر

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

 نحن نستخدم`NodeImporter` كائن لاستيراد نص إشارة مرجعية ونسخه من مستند مصدر إلى المستند الوجهة:

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

	//لنفترض أننا سنلحق بنهاية نص القسم الأخير.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// إذا قمت بالاستيراد عدة مرات بدون سياق واحد ، فسيؤدي ذلك إلى إنشاء العديد من الأنماط.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام الوظيفة Copy Bookmarked Text من Aspose.Words for .NET. اتبعنا دليلًا تفصيليًا لنسخ محتويات إشارة مرجعية من مستند مصدر إلى مستند آخر.

### الأسئلة الشائعة لنسخ النص المشار إليه في مستند Word

#### س: ما هي متطلبات استخدام ميزة "نسخ النص مع الإشارات المرجعية" في Aspose.Words for .NET؟

ج: لاستخدام ميزة "نسخ النص مع الإشارات المرجعية" في Aspose.Words for .NET ، يجب أن تكون لديك معرفة أساسية بلغة C #. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيف يمكنني تحميل مستند مصدر إلى Aspose.Words for .NET؟

 ج: لتحميل مستند مصدر في Aspose.Words for .NET ، يمكنك استخدام`Document`class عن طريق تحديد مسار ملف المستند. إليك نموذج التعليمات البرمجية:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### س: كيف تحصل على محتوى إشارة مرجعية معينة في مستند مصدر باستخدام Aspose.Words for .NET؟

 ج: للحصول على محتويات إشارة مرجعية معينة في مستند مصدر باستخدام Aspose.Words for .NET ، يمكنك الوصول إلى`Bookmarks` خاصية نطاق المستند المصدر واستخدم اسم الإشارة المرجعية لاسترداد الإشارة المرجعية المحددة. إليك نموذج التعليمات البرمجية:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### س: كيف يتم تحديد مكان نسخة نص الإشارة المرجعية في مستند الوجهة باستخدام Aspose.Words for .NET؟

 ج: لتحديد المكان الذي تريد إضافة نص إشارة مرجعية منسوخ إليه في مستند وجهة باستخدام Aspose.Words for .NET ، يمكنك الانتقال إلى نص القسم الأخير من المستند الوجهة. يمكنك استخدام ال`LastSection` الخاصية للوصول إلى القسم الأخير و`Body` خاصية الوصول إلى نص هذا القسم. إليك نموذج التعليمات البرمجية:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### س: كيفية استيراد نص الإشارة المرجعية ونسخه من المستند المصدر إلى المستند الوجهة باستخدام Aspose.Words for .NET؟

ج: لاستيراد نص إشارة مرجعية ونسخها من مستند مصدر إلى مستند وجهة باستخدام Aspose.Words for .NET ، يمكنك استخدام`NodeImporter` فئة تحدد المستند المصدر والمستند الوجهة ووضع التنسيق المطلوب الاحتفاظ به. ثم يمكنك استخدام ملف`AppendBookmarkedText` طريقة لإضافة نص الإشارة المرجعية في المستند الوجهة. إليك نموذج التعليمات البرمجية:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### س: كيف تحفظ مستند وجهة بعد نسخ نص إشارة مرجعية باستخدام Aspose.Words for .NET؟

 ج: لحفظ مستند وجهة بعد نسخ نص من إشارة مرجعية باستخدام Aspose.Words for .NET ، يمكنك استخدام`Save` طريقة`Document` كائن يحدد مسار الملف الوجهة. إليك نموذج التعليمات البرمجية:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```