---
title: فك
linktitle: فك
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية فك تشابك الإشارات المرجعية المتداخلة في صفوف الجدول المجاورة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/untangle/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Untangle في مكتبة Aspose.Words for .NET. تكشف هذه الوظيفة عن الإشارات المرجعية المتداخلة الموجودة في صفوف الجدول المجاورة.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تصفح المستندات المرجعية

نستخدم حلقة foreach للتكرار خلال جميع الإشارات المرجعية الموجودة في المستند:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // رمز للتعامل مع الإشارات المرجعية هنا
}
```

## الخطوة 2: احصل على الصفوف الأصلية من الإشارات المرجعية

 نحن نستخدم ال`GetAncestor` طرق لاسترداد الصفوف الرئيسية لعقدتي البداية والنهاية للإشارة المرجعية:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## الخطوة 3: فك الإشارات المرجعية المتداخلة

إذا تم العثور على كلا السطرين الأصليين وبدأت الإشارة المرجعية وتنتهي في أسطر متجاورة ، فإننا ننقل عقدة نهاية الإشارة المرجعية إلى نهاية الفقرة الأخيرة من الخلية الأخيرة في الصف العلوي:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### مثال على شفرة المصدر لـ Untangle باستخدام Aspose.Words for .NET

إليك مثال شفرة المصدر الكاملة لفك تشابك الإشارات المرجعية المتداخلة باستخدام Aspose.Words for .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// احصل على الصف الأصل لكل من الإشارة المرجعية وعقدة نهاية الإشارة المرجعية.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// إذا تم العثور على كلا الصفين على ما يرام ، وتم تضمين بداية الإشارة المرجعية ونهايتها في صفوف متجاورة ،
		// انقل عقدة نهاية الإشارة المرجعية إلى نهاية الفقرة الأخيرة في الخلية الأخيرة في الصف العلوي.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام وظيفة Untangle في Aspose.Words لـ .NET. لقد اتبعنا دليلًا تفصيليًا خطوة بخطوة لفك تشابك الإشارات المرجعية المتداخلة في صفوف الجدول المجاورة.