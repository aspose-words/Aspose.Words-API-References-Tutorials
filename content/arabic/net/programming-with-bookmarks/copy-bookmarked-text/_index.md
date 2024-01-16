---
title: انسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
linktitle: انسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية نسخ نص الإشارة المرجعية في مستند Word إلى مستند آخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/copy-bookmarked-text/
---

في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة نسخ النص المرجعي في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة نسخ محتويات إشارة مرجعية محددة من مستند مصدر إلى مستند آخر.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل المستند المصدر

 قبل نسخ نص الإشارة المرجعية، نحتاج إلى تحميل المستند المصدر في ملف`Document` الكائن باستخدام مسار الملف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## الخطوة 2: الحصول على الإشارة المرجعية المصدر

 نحن نستخدم ال`Bookmarks` خاصية نطاق المستند المصدر للحصول على الإشارة المرجعية المحددة التي نريد نسخها:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## الخطوة 3: إنشاء المستند الوجهة

نقوم بإنشاء مستند جديد سيكون بمثابة المستند الوجهة لنسخ محتوى الإشارة المرجعية:

```csharp
Document dstDoc = new Document();
```

## الخطوة 4: تحديد موقع النسخ

نحدد الموقع الذي نريد إضافة النص المنسوخ إليه. في مثالنا، نضيف النص إلى نهاية نص القسم الأخير من مستند الوجهة:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## الخطوة 5: استيراد ونسخ نص الإشارة المرجعية

 نحن نستخدم`NodeImporter`كائن لاستيراد ونسخ نص الإشارة المرجعية من المستند المصدر إلى المستند الوجهة:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### مثال على التعليمات البرمجية المصدر لنسخ النص المرجعي باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح نسخ النص من إشارة مرجعية باستخدام Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// هذه هي الإشارة المرجعية التي نريد نسخ محتواها.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// سنضيف إلى هذه الوثيقة.
	Document dstDoc = new Document();

	// لنفترض أنه سيتم إلحاقنا بنهاية نص القسم الأخير.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// إذا قمت بالاستيراد عدة مرات دون سياق واحد، فسيؤدي ذلك إلى إنشاء العديد من الأنماط.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### إلحاق رمز مصدر النص المرجعي

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // هذه هي الفقرة التي تحتوي على بداية الإشارة المرجعية.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // هذه هي الفقرة التي تحتوي على نهاية الإشارة المرجعية.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // نقتصر على سيناريو بسيط إلى حد معقول.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // نريد نسخ جميع الفقرات من فقرة البداية حتى (بما في ذلك) الفقرة النهاية،
            // وبالتالي فإن العقدة التي نتوقف عندها هي واحدة بعد نهاية الفقرة.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //يؤدي هذا إلى إنشاء نسخة من العقدة الحالية واستيرادها (مما يجعلها صالحة) في السياق
                // من وثيقة الوجهة. الاستيراد يعني تعديل الأنماط ومعرفات القائمة بشكل صحيح.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة نسخ النص المرجعي من Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لنسخ محتويات الإشارة المرجعية من مستند مصدر إلى مستند آخر.

### الأسئلة الشائعة لنسخ النص الذي تم وضع إشارة مرجعية عليه في مستند Word

#### س: ما هي متطلبات استخدام ميزة "نسخ النص مع الإشارات المرجعية" في Aspose.Words for .NET؟

ج: لاستخدام ميزة "نسخ النص مع الإشارات المرجعية" في Aspose.Words لـ .NET، يجب أن تكون لديك معرفة أساسية بلغة C#. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيف يمكنني تحميل مستند مصدر إلى Aspose.Words لـ .NET؟

 ج: لتحميل مستند مصدر في Aspose.Words لـ .NET، يمكنك استخدام`Document` فئة عن طريق تحديد مسار ملف الوثيقة. هنا نموذج التعليمات البرمجية:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### س: كيف يمكن الحصول على محتوى إشارة مرجعية معينة في مستند مصدر باستخدام Aspose.Words for .NET؟

 ج: للحصول على محتويات إشارة مرجعية معينة في مستند مصدر باستخدام Aspose.Words for .NET، يمكنك الوصول إلى`Bookmarks` خاصية نطاق المستند المصدر واستخدم اسم الإشارة المرجعية لاسترداد الإشارة المرجعية المحددة. هنا نموذج التعليمات البرمجية:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### س: كيفية تحديد موقع النسخة النصية للإشارة المرجعية في المستند الوجهة باستخدام Aspose.Words for .NET؟

 ج: لتحديد المكان الذي تريد إضافة نص الإشارة المرجعية المنسوخ فيه في المستند الوجهة باستخدام Aspose.Words for .NET، يمكنك الانتقال إلى نص القسم الأخير من المستند الوجهة. يمكنك استخدام ال`LastSection` خاصية للوصول إلى القسم الأخير و`Body` الخاصية للوصول إلى نص هذا القسم. هنا نموذج التعليمات البرمجية:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### س: كيفية استيراد ونسخ نص الإشارة المرجعية من المستند المصدر إلى المستند الوجهة باستخدام Aspose.Words for .NET؟

 ج: لاستيراد نص الإشارة المرجعية ونسخه من مستند مصدر إلى مستند وجهة باستخدام Aspose.Words for .NET، يمكنك استخدام`NodeImporter` فئة تحدد المستند المصدر والمستند الوجهة ووضع التنسيق المطلوب الاحتفاظ به. ثم يمكنك استخدام`AppendBookmarkedText` طريقة لإضافة نص الإشارة المرجعية في المستند الوجهة. هنا نموذج التعليمات البرمجية:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### س: كيف يمكن حفظ مستند الوجهة بعد نسخ نص الإشارة المرجعية باستخدام Aspose.Words لـ .NET؟

ج: لحفظ مستند وجهة بعد نسخ النص من إشارة مرجعية باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Save` طريقة`Document` كائن يحدد مسار الملف الوجهة. هنا نموذج التعليمات البرمجية:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```