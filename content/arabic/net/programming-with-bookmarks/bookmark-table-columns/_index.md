---
title: إشارة مرجعية لأعمدة الجدول في مستند Word
linktitle: إشارة مرجعية لأعمدة الجدول في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية وضع إشارة مرجعية على عمود جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/bookmark-table-columns/
---

في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة Bookmark Table Columns في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة وضع إشارة مرجعية على عمود معين من الجدول في مستند Word والوصول إلى محتوى هذا العمود.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء الجدول

 قبل إنشاء إشارة مرجعية على عمود الجدول، يجب علينا أولاً إنشاء الجدول باستخدام`DocumentBuilder`هدف. في مثالنا، قمنا بإنشاء جدول مكون من صفين وعمودين:

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

## الخطوة 2: إنشاء الإشارة المرجعية للعمود

 نحن نستخدم ال`StartBookmark` طريقة لإنشاء إشارة مرجعية على عمود معين في الجدول. في مثالنا، نستخدم اسم "MyBookmark" للإشارة المرجعية:

```csharp
builder. StartBookmark("MyBookmark");
```

## الخطوة 3: الوصول إلى محتوى العمود

 نتصفح جميع الإشارات المرجعية الموجودة في المستند ونعرض أسمائها. إذا كانت الإشارة المرجعية عبارة عن عمود، فيمكننا الوصول إلى محتويات هذا العمود باستخدام فهرس العمود و`GetText` طريقة:

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

### مثال على التعليمات البرمجية المصدر لأعمدة جدول الإشارات المرجعية باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح كيفية إنشاء إشارة مرجعية على عمود جدول باستخدام Aspose.Words for .NET:

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

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة الإشارة المرجعية لأعمدة الجدول في Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لوضع إشارة مرجعية على عمود معين من الجدول في مستند Word والانتقال إلى محتويات هذا العمود.

### الأسئلة الشائعة حول أعمدة جدول الإشارات المرجعية في مستند Word

#### س: ما هي المتطلبات الأساسية لاستخدام ميزة "الإشارات المرجعية لأعمدة الجدول" في Aspose.Words for .NET؟

ج: لاستخدام ميزة "الإشارات المرجعية لأعمدة الجدول" في Aspose.Words لـ .NET، يجب أن تكون لديك معرفة أساسية بلغة C#. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س: كيفية إنشاء جدول يحتوي على أعمدة في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء جدول يحتوي على أعمدة في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`DocumentBuilder` كائن لإدراج الخلايا والمحتوى في الجدول. هنا نموذج التعليمات البرمجية:

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

#### س: كيفية وضع إشارة مرجعية على عمود جدول باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء إشارة مرجعية على عمود جدول باستخدام Aspose.Words لـ .NET، يمكنك استخدام`StartBookmark` طريقة`DocumentBuilder` كائن لبدء الإشارة المرجعية في عمود جدول محدد. هنا نموذج التعليمات البرمجية:

```csharp
builder.StartBookmark("MyBookmark");
```

#### س: كيفية الوصول إلى محتوى عمود الجدول من الإشارة المرجعية باستخدام Aspose.Words لـ .NET؟

ج: للوصول إلى محتويات عمود جدول من إشارة مرجعية باستخدام Aspose.Words لـ .NET، يمكنك تكرار جميع الإشارات المرجعية في المستند، والتحقق مما إذا كانت الإشارة المرجعية عبارة عن عمود، واستخدام فهرس العمود للوصول إلى محتويات هذا العمود. هنا نموذج التعليمات البرمجية:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // افعل شيئًا بمحتويات العمود ...
         }
     }
}
```

#### س: هل هناك حد لعدد الأعمدة التي يمكنني إنشاؤها في جدول يحتوي على إشارات مرجعية للأعمدة؟

ج: لا يوجد حد محدد لعدد الأعمدة التي يمكنك إنشاؤها في جدول يحتوي على إشارات مرجعية للأعمدة باستخدام Aspose.Words for .NET. يعتمد الحد بشكل أساسي على الموارد المتاحة على نظامك ومواصفات تنسيق ملف Word الذي تستخدمه. ومع ذلك، يوصى بعدم إنشاء عدد كبير جدًا من الأعمدة، حيث يمكن أن يؤثر ذلك على أداء المستند النهائي وقابليته للقراءة.