---
title: الوصول إلى الإشارات المرجعية
linktitle: الوصول إلى الإشارات المرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الوصول إلى الإشارات المرجعية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/access-bookmarks/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة إشارات مرجعية في Aspose.Words for .NET library. توفر هذه الميزة الوصول إلى إشارات مرجعية محددة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل المستند

 قبل أن نبدأ في الوصول إلى الإشارات المرجعية ، نحتاج إلى تحميل مستند Word باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` كائن يحدد مسار ملف المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## الخطوة 2: الوصول إلى الإشارات المرجعية

بمجرد تحميل المستند ، يمكننا الوصول إلى الإشارات المرجعية في المستند. هناك طريقتان للوصول إلى الإشارات المرجعية: عن طريق الفهرس والاسم.

- الوصول عن طريق الفهرس: في مثالنا ، نستخدم الفهرس 0 للوصول إلى الإشارة المرجعية الأولى للمستند:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- الوصول بالاسم: في مثالنا ، نستخدم الاسم "MyBookmark3" للوصول إلى إشارة مرجعية معينة في المستند:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### مثال على شفرة المصدر للوصول إلى الإشارات المرجعية باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح الوصول إلى الإشارات المرجعية باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// حسب الفهرس:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// بالاسم:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام ميزة Access Bookmarks في Aspose.Words for .NET. اتبعنا دليلًا تفصيليًا لتحميل مستند والوصول إلى الإشارات المرجعية باستخدام الفهرس والاسم.