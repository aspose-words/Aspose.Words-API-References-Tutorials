---
title: حذف الصف حسب الإشارة المرجعية
linktitle: حذف الصف حسب الإشارة المرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية حذف صف جدول بناءً على إشارة مرجعية معينة في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/delete-row-by-bookmark/
---

في هذه المقالة ، سوف نستكشف كود المصدر C # أعلاه لفهم كيفية استخدام وظيفة حذف الصف حسب الإشارة المرجعية في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة حذف صف جدول بناءً على إشارة مرجعية معينة في المستند.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على الإشارة المرجعية

 نحن نستخدم ال`Bookmarks`خاصية نطاق المستند للحصول على الإشارة المرجعية المحددة التي نريد استخدامها لحذف صف الجدول:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## الخطوة 2: حذف صف الجدول

 نحن نستخدم ال`GetAncestor` طريقة الحصول على`Row` اكتب العنصر الأصل للإشارة المرجعية. بعد ذلك ، نستخدم ملف`Remove` طريقة إزالة صف الجدول:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### مثال على شفرة المصدر لـ Delete Row By Bookmark باستخدام Aspose.Words for .NET

إليك نموذج التعليمات البرمجية المصدر الكامل لتوضيح حذف صف جدول بناءً على إشارة مرجعية معينة باستخدام Aspose.Words for .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام وظيفة حذف الصف حسب الإشارة المرجعية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا خطوة بخطوة لحذف صف جدول بناءً على إشارة مرجعية محددة في المستند.