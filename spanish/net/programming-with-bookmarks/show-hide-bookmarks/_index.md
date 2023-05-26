---
title: إظهار إخفاء الإشارات المرجعية
linktitle: إظهار إخفاء الإشارات المرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إظهار أو إخفاء إشارة مرجعية معينة في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarks/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة إظهار إخفاء الإشارات المرجعية في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إظهار أو إخفاء إشارة مرجعية معينة في المستند.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل المستند

 نحن نستخدم ال`Document` فئة لتحميل المستند الحالي من ملف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## الخطوة 2: إظهار أو إخفاء إشارة مرجعية معينة

 نحن نستخدم ال`ShowHideBookmarkedContent` وظيفة لإظهار أو إخفاء إشارة مرجعية معينة في المستند. تأخذ هذه الوظيفة كمعلمات للمستند واسم الإشارة المرجعية وقيمة منطقية للإشارة إلى ما إذا كان سيتم إظهار الإشارة المرجعية أو إخفائها:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## الخطوة 3: حفظ المستند المعدل

 نحن نستخدم ال`Save` طريقة لحفظ المستند المعدل في ملف:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### مثال على شفرة المصدر لـ Show Hide Bookmarks باستخدام Aspose.Words for .NET

إليك المثال الكامل لشفرة المصدر لتوضيح إظهار أو إخفاء إشارة مرجعية معينة باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام ميزة إظهار إخفاء الإشارات المرجعية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإظهار أو إخفاء إشارة مرجعية معينة في مستند.