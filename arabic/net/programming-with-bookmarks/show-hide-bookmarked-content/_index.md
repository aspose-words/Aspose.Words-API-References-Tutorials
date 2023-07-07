---
title: إظهار إخفاء المحتوى الذي تم وضع إشارة مرجعية عليه
linktitle: إظهار إخفاء المحتوى الذي تم وضع إشارة مرجعية عليه
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إظهار أو إخفاء محتوى الإشارات المرجعية باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة إظهار إخفاء المحتوى المرتبط بإشارة مرجعية في Aspose.Words for .NET library. تتيح لك هذه الميزة إظهار أو إخفاء محتويات إشارة مرجعية بناءً على شرط معين عند دمج البيانات.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على الإشارة المرجعية

 نحن نستخدم ال`Bookmarks` خاصية نطاق المستند للحصول على الإشارة المرجعية المحددة التي نريد إظهار المحتوى أو إخفائه:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## الخطوة 2: إدراج حقول الدمج

 نحن نستخدم منشئ المستندات`DocumentBuilder` لإدراج حقول الدمج الضرورية. ستعمل حقول الدمج هذه على تعيين شرط لإظهار أو إخفاء محتوى الإشارة المرجعية بناءً على قيمة`showHide` عامل:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## الخطوة 3: نقل محتوى الإشارة المرجعية

ندور محتويات الإشارة المرجعية وننقلها حتى تظهر

ISSE قبل الإشارة المرجعية. سيتحكم هذا في إظهار المحتوى أو إخفائه بناءً على الشرط المحدد:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## الخطوة 4: نقل باقي محتوى الإشارة المرجعية

نقوم بنقل باقي محتوى الإشارة المرجعية بعد الإشارة المرجعية ، باستخدام عقدة نهاية الإشارة المرجعية كنقطة إدخال:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## الخطوة 5: تنفيذ الدمج

 نحن نستخدم ال`Execute` طريقة الوثيقة`s `دمج المراسلات` object to execute the merge using the bookmark name and the value of the `متغير showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### مثال على شفرة المصدر لـ Show Hide Bookmarked Content باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح إظهار أو إخفاء محتوى الإشارة المرجعية باستخدام Aspose.Words for .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {إذا كان "{MERGEFIELD إشارة مرجعية}" = "صحيح" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام ميزة إظهار إخفاء المحتوى المرتبط بإشارة مرجعية في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإظهار أو إخفاء محتويات إشارة مرجعية بناءً على شرط معين عند دمج البيانات.