---
title: إظهار إخفاء المحتوى ذي الإشارة المرجعية في مستند Word
linktitle: إظهار إخفاء المحتوى ذي الإشارة المرجعية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إظهار أو إخفاء محتوى الإشارة المرجعية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة إظهار إخفاء المحتوى المرجعي في مكتبة Aspose.Words لـ .NET. تتيح لك هذه الميزة إظهار أو إخفاء محتويات الإشارة المرجعية في مستند Word بناءً على شرط معين عند دمج البيانات.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على الإشارة المرجعية

 نحن نستخدم ال`Bookmarks` خاصية نطاق المستند للحصول على الإشارة المرجعية المحددة التي نريد إظهار أو إخفاء المحتوى عليها:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## الخطوة 2: إدراج حقول الدمج

 نحن نستخدم منشئ المستندات`DocumentBuilder` لإدراج حقول الدمج الضرورية. ستقوم حقول الدمج هذه بتعيين شرط لإظهار أو إخفاء محتوى الإشارة المرجعية اعتمادًا على قيمة`showHide` عامل:

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

نقوم بمراجعة محتويات الإشارة المرجعية ونحركها حتى تظهر

isse قبل الإشارة المرجعية. سيتحكم هذا في إظهار المحتوى أو إخفائه بناءً على الشرط المحدد:

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

## الخطوة 4: نقل بقية محتوى الإشارة المرجعية

نقوم بنقل بقية محتوى الإشارة المرجعية بعد الإشارة المرجعية، باستخدام العقدة النهائية للإشارة المرجعية كنقطة إدراج:

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

 نحن نستخدم ال`Execute` طريقة الوثيقة`s `دمج المراسلات` object to execute the merge using the bookmark name and the value of the `showHide` المتغير:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### مثال على التعليمات البرمجية المصدر لـ Show Hide Bookmarked Content باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل لكود المصدر لتوضيح إظهار أو إخفاء محتوى الإشارة المرجعية باستخدام Aspose.Words for .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {إذا "{إشارة مرجعية MERGEFIELD}" = "صحيح" "" ""}
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

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام ميزة إظهار إخفاء المحتوى المرتبط بإشارة مرجعية في Aspose.Words for .NET. لقد اتبعنا دليلاً خطوة بخطوة لإظهار أو إخفاء محتويات الإشارة المرجعية بناءً على حالة معينة عند دمج البيانات.

### الأسئلة الشائعة لإظهار إخفاء المحتوى ذي الإشارة المرجعية في مستند Word

#### س: هل يمكنني استخدام نفس الشرط لإشارات مرجعية متعددة في نفس المستند؟

 ج: نعم، يمكنك استخدام نفس الشرط لإشارات مرجعية متعددة في نفس المستند. ما عليك سوى تكرار الخطوات من 2 إلى 5 لكل إشارة مرجعية، وضبط اسم الإشارة المرجعية واختياريًا قيمة`showhide` متغير حسب الحاجة.

#### س: كيف يمكنني إضافة المزيد من الشروط لإظهار أو إخفاء محتوى الإشارة المرجعية؟

 ج: لإضافة المزيد من الشروط، يمكنك استخدام عوامل التشغيل المنطقية مثل`AND` و`OR` في الكود الخاص بإدراج حقول الدمج في الخطوة 2. قم بتحرير الشرط في الكود التالي لإضافة شروط إضافية:

```csharp
builder. Write("\" = \"true\" ");
```

#### س: كيف يمكنني حذف إشارة مرجعية في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لإزالة إشارة مرجعية في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Remove` الطريقة من`Bookmarks` مجموعة من نطاق الوثيقة. فيما يلي نموذج التعليمات البرمجية لحذف إشارة مرجعية محددة:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### س: هل مكتبة Aspose.Words مجانية؟

 ج: مكتبة Aspose.Words هي مكتبة تجارية وتتطلب ترخيصًا صالحًا لاستخدامها في مشاريعك. يمكنك التحقق[Aspose.Words لمراجع .NET API](https://reference.aspose.com/words/net/) لمعرفة المزيد حول خيارات الترخيص والأسعار.

#### س: هل توجد مكتبات أخرى متاحة لمعالجة الكلمات باستخدام مستندات Word في .NET؟

ج: نعم، هناك مكتبات أخرى متاحة لمعالجة الكلمات باستخدام مستندات Word في .NET، مثل Open XML SDK وGemBox.Document. يمكنك استكشاف هذه المكتبات كبدائل لـ Aspose.Words بناءً على احتياجاتك وتفضيلاتك المحددة.