---
title: إلحاق نص تم وضع إشارة مرجعية عليه في مستند Word
linktitle: إلحاق نص تم وضع إشارة مرجعية عليه في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إضافة نص من إشارة مرجعية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/append-bookmarked-text/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Append Bookmarked Text في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة إضافة النص الموجود في إشارة مرجعية معينة لمستند Word إلى مستند آخر.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على فقرات من المرجعية

 قبل أن نبدأ في إضافة نص الإشارة المرجعية ، نحتاج إلى الحصول على الفقرات التي تحتوي على بداية الإشارة المرجعية ونهايتها. يمكن القيام بذلك عن طريق الوصول إلى`BookmarkStart` و`BookmarkEnd` خصائص المرجعية:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## الخطوة 2: تحقق من الفقرات الأصلية

نتحقق مما إذا كانت فقرات البداية والنهاية لها أبوين صالحان ، أي إذا كانت تنتمي حقًا إلى فقرة. إذا لم يكن الأمر كذلك ، فإننا ننشئ استثناءً:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## الخطوة 3: تحقق من آباء الفقرات

نتحقق مما إذا كانت فقرات البداية والنهاية لها نفس الأصل. إذا لم يكن الأمر كذلك ، فهذا يعني أن الفقرات ليست موجودة في نفس القسم أو المستند ، ونحن نطرح استثناءً:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## الخطوة 4: انسخ الفقرات

نقوم بالتكرار خلال العقد (الفقرات) من فقرة البداية إلى فقرة النهاية. لكل عقدة ، نقوم بإنشاء نسخة واستيرادها في سياق المستند الوجهة:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### مثال على شفرة المصدر لإلحاق نص مرجعي باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح إضافة نص من إشارة مرجعية باستخدام Aspose.Words for .NET:

```csharp

	// هذه هي الفقرة التي تحتوي على بداية الإشارة المرجعية.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// هذه هي الفقرة التي تحتوي على نهاية الإشارة المرجعية.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// نقصر أنفسنا على سيناريو بسيط إلى حد معقول.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// نريد نسخ جميع الفقرات من فقرة البداية حتى (بما في ذلك) الفقرة النهائية ،
	// لذلك فإن العقدة التي نتوقف عندها هي واحدة بعد نهاية الفقرة.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// يؤدي هذا إلى إنشاء نسخة من العقدة الحالية واستيرادها (يجعلها صالحة) في السياق
		// من وثيقة الوجهة. الاستيراد يعني تعديل الأنماط ومعرفات القوائم بشكل صحيح.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Append Bookmarked Text في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا للحصول على فقرات من إشارة مرجعية ، والتحقق من الوالدين ، ونسخ الفقرات إلى مستند آخر.

### الأسئلة الشائعة لإلحاق نص تم وضع إشارة مرجعية عليه في مستند Word

#### س 1: ما هي المتطلبات الأساسية لاستخدام ميزة "إضافة نص مع الإشارات المرجعية" في Aspose.Words for .NET؟

ج: لاستخدام وظيفة "إضافة نص مع إشارات مرجعية" في Aspose.Words for .NET ، يجب أن تكون لديك معرفة أساسية بلغة C #. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س 2: كيف تحصل على الفقرات التي تحتوي على بداية ونهاية إشارة مرجعية في مستند Word؟

 ج: للحصول على الفقرات التي تحتوي على بداية ونهاية إشارة مرجعية في مستند Word ، يمكنك الوصول إلى ملف`BookmarkStart` و`BookmarkEnd` خصائص الإشارة المرجعية. إليك نموذج التعليمات البرمجية:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### س 3: ماذا يحدث إذا كانت فقرات البداية والنهاية لا تحتوي على أبوين صالحين؟

ج: إذا كانت فقرات البداية والنهاية لا تحتوي على أبوين صالحين ، أي أنهما ليسا فقرتين بالفعل ، فسيتم طرح استثناء. لا يمكن إدارة هذا الوضع في هذا الوقت.
