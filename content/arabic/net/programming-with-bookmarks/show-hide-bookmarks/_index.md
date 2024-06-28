---
title: إظهار إخفاء الإشارات المرجعية في مستند Word
linktitle: إظهار إخفاء الإشارات المرجعية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إظهار أو إخفاء إشارة مرجعية معينة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/show-hide-bookmarks/
---

في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة إظهار إخفاء الإشارات المرجعية في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إظهار أو إخفاء إشارة مرجعية محددة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: تحميل الوثيقة

 نحن نستخدم ال`Document` فئة لتحميل المستند الموجود من ملف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## الخطوة 2: إظهار أو إخفاء إشارة مرجعية محددة

 نحن نستخدم ال`ShowHideBookmarkedContent` وظيفة لإظهار أو إخفاء إشارة مرجعية معينة في المستند. تأخذ هذه الوظيفة المستند واسم الإشارة المرجعية وقيمة منطقية كمعلمات للإشارة إلى ما إذا كان سيتم إظهار الإشارة المرجعية أو إخفائها:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## الخطوة 3: حفظ المستند المعدل

 نحن نستخدم ال`Save` طريقة حفظ المستند المعدل في ملف:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### مثال على التعليمات البرمجية المصدر لإظهار إخفاء الإشارات المرجعية باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح إظهار أو إخفاء إشارة مرجعية معينة باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent كود المصدر

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام ميزة إظهار إخفاء الإشارات المرجعية في Aspose.Words for .NET. لقد اتبعنا دليلاً خطوة بخطوة لإظهار أو إخفاء إشارة مرجعية معينة في المستند.

### الأسئلة الشائعة لإظهار إخفاء الإشارات المرجعية في مستند Word

#### س: هل يمكنني إظهار أو إخفاء إشارات مرجعية متعددة في نفس المستند؟

ج: نعم، يمكنك إظهار أو إخفاء إشارات مرجعية متعددة في نفس المستند عن طريق تكرار الخطوتين 2 و3 لكل إشارة مرجعية تريد معالجتها.

#### س: هل تعمل التعليمات البرمجية المتوفرة مع تنسيقات مستندات Word الأخرى، مثل ‎.doc أو ‎.docm؟

ج: نعم، يعمل الكود المقدم مع تنسيقات مستندات Word المختلفة التي يدعمها Aspose.Words، مثل .doc و.docm. فقط تأكد من استخدام اسم الملف والمسار الصحيحين عند تحميل المستند وحفظه.

#### س: كيف يمكنني إظهار إشارة مرجعية مخفية مرة أخرى؟

 ج: لإظهار إشارة مرجعية مخفية مرة أخرى، عليك استخدام نفس الإشارة`ShowHideBookmarkedContent` وظيفة تمرير القيمة`true` للمعلمة المنطقية التي تشير إلى إظهار الإشارة المرجعية أو إخفائها.

#### س: هل يمكنني استخدام الشروط لإظهار أو إخفاء الإشارات المرجعية بناءً على قيم حقول الدمج في المستند؟

 ج: نعم، يمكنك استخدام الشروط ودمج قيم الحقول لتحديد ما إذا كان يجب إظهار الإشارة المرجعية أم إخفائها. يمكنك تخصيص رمز`ShowHideBookmarkedContent` وظيفة لمراعاة الظروف والقيم المناسبة.

#### س: كيف يمكنني حذف إشارة مرجعية في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: لإزالة إشارة مرجعية في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`RemoveBookmarks` طريقة`Document` فصل. هنا نموذج التعليمات البرمجية:

```csharp
doc.RemoveBookmarks("BookmarkName");
```