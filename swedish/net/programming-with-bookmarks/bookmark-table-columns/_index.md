---
title: أعمدة الجدول المرجعية
linktitle: أعمدة الجدول المرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية وضع إشارة مرجعية على عمود جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/bookmark-table-columns/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة أعمدة جدول الإشارات المرجعية في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة وضع إشارة مرجعية على عمود معين من الجدول في مستند Word والوصول إلى محتوى هذا العمود.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء الجدول

 قبل إنشاء إشارة مرجعية على عمود جدول ، يجب علينا أولاً إنشاء الجدول باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نقوم بإنشاء جدول من صفين وعمودين:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## الخطوة 2: إنشاء إشارة مرجعية للعمود

 نحن نستخدم ال`StartBookmark`طريقة لإنشاء إشارة مرجعية على عمود معين من الجدول. في مثالنا ، نستخدم اسم "MyBookmark" للإشارة المرجعية:

```csharp
builder. StartBookmark("MyBookmark");
```

## الخطوة 3: الوصول إلى محتوى العمود

 نتصفح جميع الإشارات المرجعية في المستند ونعرض أسمائها. إذا كانت الإشارة المرجعية عبارة عن عمود ، فإننا نصل إلى محتويات ذلك العمود باستخدام فهرس العمود وملف`GetText` طريقة:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### مثال على شفرة المصدر لأعمدة جدول الإشارات باستخدام Aspose.Words for .NET

إليك نموذج شفرة المصدر الكامل لتوضيح إنشاء إشارة مرجعية في عمود الجدول باستخدام Aspose.Words for .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة أعمدة جدول الإشارات المرجعية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لوضع إشارة مرجعية على عمود معين من الجدول في مستند Word والانتقال إلى محتويات هذا العمود.