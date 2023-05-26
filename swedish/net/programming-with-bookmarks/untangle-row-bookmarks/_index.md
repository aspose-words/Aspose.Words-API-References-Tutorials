---
title: فك الإشارات المرجعية في الصف
linktitle: فك الإشارات المرجعية في الصف
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية فك تشابك الإشارات المرجعية للصفوف المتداخلة لإزالة صفوف معينة دون التأثير على الإشارات المرجعية الأخرى.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/untangle-row-bookmarks/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Untangle Row Bookmarks في Aspose.Words for .NET library. تتيح هذه الوظيفة إمكانية وضع نهايات الإشارات المرجعية للسطر في نفس السطر مثل بدايات الإشارات المرجعية.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل المستند

 نحن نستخدم ال`Document` فئة لتحميل المستند الحالي من ملف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## الخطوة 2: كشف خط الإشارات المرجعية

 نحن نستخدم ال`Untangle` وظيفة لفك تشابك الإشارات المرجعية من الصفوف. تؤدي هذه الوظيفة المهمة المخصصة لوضع نهايات الأسطر المرجعية في نفس السطر الذي تبدأ فيه الإشارة المرجعية:

```csharp
Untangle(doc);
```

## الخطوة 3: حذف سطر بإشارة مرجعية

 نحن نستخدم ال`DeleteRowByBookmark` وظيفة لحذف صف معين من خلال الإشارة المرجعية الخاصة به:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## الخطوة 4: التحقق من سلامة الإشارات المرجعية الأخرى

نتحقق من عدم تلف الإشارات المرجعية الأخرى عن طريق التحقق مما إذا كانت نهاية الإشارة المرجعية لا تزال موجودة:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### مثال على شفرة المصدر لـ Untangle Row Bookmarks باستخدام Aspose.Words for .NET**

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لفك تشابك الإشارات المرجعية من الأسطر باستخدام Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//يؤدي ذلك إلى تنفيذ المهمة المخصصة لوضع إشارة مرجعية للصف في نفس الصف مع بدء الإشارة المرجعية.
	Untangle(doc);

	// يمكننا الآن حذف الصفوف بسهولة بواسطة إشارة مرجعية دون الإضرار بأي إشارات مرجعية للصفوف الأخرى.
	DeleteRowByBookmark(doc, "ROW2");

	// هذا فقط للتحقق من عدم تلف الإشارة المرجعية الأخرى.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام ميزة Untangle Row Bookmarks في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا خطوة بخطوة لفك تشابك الإشارات المرجعية للصفوف وحذف صف معين دون الإضرار بالإشارات المرجعية الأخرى.