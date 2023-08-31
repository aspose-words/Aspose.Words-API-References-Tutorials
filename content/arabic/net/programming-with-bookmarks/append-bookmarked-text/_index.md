---
title: إلحاق نص مرجعي في مستند Word
linktitle: إلحاق نص مرجعي في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة نص من إشارة مرجعية في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/append-bookmarked-text/
---

في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة إلحاق نص مرجعي في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة إضافة النص الموجود في إشارة مرجعية محددة لمستند Word إلى مستند آخر.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على الفقرات من الإشارة المرجعية

 قبل أن نبدأ بإضافة نص الإشارة المرجعية، نحتاج إلى الحصول على الفقرات التي تحتوي على بداية ونهاية الإشارة المرجعية. ويمكن القيام بذلك عن طريق الوصول إلى`BookmarkStart` و`BookmarkEnd` خصائص المرجعية:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## الخطوة 2: التحقق من الفقرات الأصل

نحن نتحقق مما إذا كانت فقرات البداية والنهاية لها أصول صالحة، أي إذا كانت تنتمي بالفعل إلى فقرة ما. إذا لم يكن الأمر كذلك، فإننا ننشئ استثناءً:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## الخطوة 3: التحقق من آباء الفقرات

نتحقق مما إذا كانت فقرات البداية والنهاية لهما نفس الأصل. إذا لم يكن الأمر كذلك، فهذا يعني أن الفقرات غير موجودة في نفس القسم أو المستند، ونحن نطرح استثناءً:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## الخطوة 4: نسخ الفقرات

نقوم بالتكرار عبر العقد (الفقرات) من فقرة البداية إلى فقرة النهاية. لكل عقدة، نقوم بإنشاء نسخة واستيرادها في سياق المستند الوجهة:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### مثال على التعليمات البرمجية المصدر لإلحاق نص مرجعي باستخدام Aspose.Words لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتوضيح إضافة نص من إشارة مرجعية باستخدام Aspose.Words لـ .NET:

```csharp

	// هذه هي الفقرة التي تحتوي على بداية الإشارة المرجعية.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// هذه هي الفقرة التي تحتوي على نهاية الإشارة المرجعية.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// نقتصر على سيناريو بسيط إلى حد معقول.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// نريد نسخ جميع الفقرات من فقرة البداية حتى (بما في ذلك) الفقرة النهاية،
	// وبالتالي فإن العقدة التي نتوقف عندها هي واحدة بعد نهاية الفقرة.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// يؤدي هذا إلى إنشاء نسخة من العقدة الحالية واستيرادها (مما يجعلها صالحة) في السياق
		// من وثيقة الوجهة. الاستيراد يعني تعديل الأنماط ومعرفات القائمة بشكل صحيح.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة إلحاق نص مرجعي في Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة للحصول على فقرات من إشارة مرجعية، والتحقق من الأصول، ونسخ الفقرات إلى مستند آخر.

### الأسئلة الشائعة لإلحاق نص بإشارة مرجعية في مستند Word

#### س1: ما هي المتطلبات الأساسية لاستخدام ميزة "إضافة نص مع الإشارات المرجعية" في Aspose.Words لـ .NET؟

ج: لاستخدام وظيفة "إضافة نص مع إشارات مرجعية" في Aspose.Words لـ .NET، يجب أن تكون لديك معرفة أساسية بلغة C#. تحتاج أيضًا إلى بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

#### س2: كيفية الحصول على الفقرات التي تحتوي على بداية ونهاية الإشارة المرجعية في مستند Word؟

 ج: للحصول على الفقرات التي تحتوي على بداية ونهاية الإشارة المرجعية في مستند Word، يمكنك الوصول إلى`BookmarkStart` و`BookmarkEnd` خصائص المرجعية. هنا نموذج التعليمات البرمجية:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### س3: ماذا يحدث إذا لم يكن لفقرات البداية والنهاية أصول صحيحة؟

ج: إذا لم يكن لفقرات البداية والنهاية أصول صحيحة، أي أنها ليست فقرات حقيقية، فسيتم طرح استثناء. لا يمكن إدارة هذا الوضع في هذا الوقت.
