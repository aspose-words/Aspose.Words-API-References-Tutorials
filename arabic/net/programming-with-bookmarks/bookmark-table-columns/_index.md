---
title: ضع إشارة مرجعية على أعمدة الجدول في مستند Word
linktitle: ضع إشارة مرجعية على أعمدة الجدول في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية وضع إشارة مرجعية على عمود جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/bookmark-table-columns/
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

 نحن نستخدم ال`StartBookmark` طريقة لإنشاء إشارة مرجعية على عمود معين من الجدول. في مثالنا ، نستخدم اسم "MyBookmark" للإشارة المرجعية:

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

### الأسئلة الشائعة حول أعمدة جدول الإشارات المرجعية في مستند Word

#### س: ما هي المتطلبات الأساسية لاستخدام ميزة "الإشارات المرجعية لأعمدة الجدول" في Aspose.Words for .NET؟

ج: لاستخدام ميزة "الإشارات المرجعية لأعمدة الجدول" في Aspose.Words for .NET ، يجب أن تكون لديك معرفة أساسية بلغة C #. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيفية إنشاء جدول بأعمدة في مستند Word باستخدام Aspose.Words for .NET؟

 ج: لإنشاء جدول بأعمدة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام ملف`DocumentBuilder`كائن لإدراج الخلايا والمحتوى في الجدول. إليك نموذج التعليمات البرمجية:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### س: كيف يمكن وضع إشارة مرجعية على عمود جدول باستخدام Aspose.Words for .NET؟

 ج: لإنشاء إشارة مرجعية في عمود جدول باستخدام Aspose.Words for .NET ، يمكنك استخدام`StartBookmark` طريقة`DocumentBuilder` كائن لبدء الإشارة المرجعية على عمود جدول معين. إليك نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("MyBookmark");
```

#### س: كيف يمكن الوصول إلى محتوى عمود الجدول من الإشارة المرجعية باستخدام Aspose.Words for .NET؟

ج: للوصول إلى محتويات عمود جدول من إشارة مرجعية باستخدام Aspose.Words for .NET ، يمكنك تكرار جميع الإشارات المرجعية في المستند ، والتحقق مما إذا كانت الإشارة المرجعية عبارة عن عمود ، واستخدام فهرس العمود للوصول إلى محتويات هذا العمود. إليك نموذج التعليمات البرمجية:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // افعل شيئًا ما بمحتويات العمود ...
         }
     }
}
```

#### س: هل هناك حد لعدد الأعمدة التي يمكنني إنشاؤها في جدول يحتوي على إشارات مرجعية للعمود؟

ج: لا يوجد حد معين لعدد الأعمدة التي يمكنك إنشاؤها في جدول مع إشارات مرجعية للعمود باستخدام Aspose.Words for .NET. يعتمد الحد بشكل أساسي على الموارد المتاحة على نظامك ومواصفات تنسيق ملف Word الذي تستخدمه. ومع ذلك ، يوصى بعدم إنشاء عدد كبير جدًا من الأعمدة ، حيث يمكن أن يؤثر ذلك على أداء المستند النهائي وسهولة قراءته.