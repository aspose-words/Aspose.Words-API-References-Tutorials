---
title: حسب الأقسام
linktitle: حسب الأقسام
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تقسيم مستند Word إلى أقسام منفصلة باستخدام Aspose.Words for .NET مع مثال رمز كامل.
type: docs
weight: 10
url: /sv/net/split-document/by-sections/
---

في هذا المثال ، سنوضح لك كيفية تقسيم مستند Word إلى أقسام منفصلة باستخدام ميزة حسب الأقسام في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر والحصول على مستندات منفصلة لكل قسم.

## الخطوة 1: تحميل المستند

للبدء ، نحتاج إلى تحديد دليل المستند الخاص بك وتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## الخطوة 2: قسّم المستند إلى أقسام

سنقوم الآن بالتكرار خلال كل قسم من المستند وتقسيم المستند إلى أجزاء أصغر ، قسمًا قسمًا. هيريس كيفية القيام بذلك:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// قسّم المستند إلى أجزاء أصغر ، في هذه الحالة ، افصله حسب القسم.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// احفظ كل قسم كمستند منفصل.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### مثال على شفرة المصدر لـ By Sections باستخدام Aspose.Words for .NET

فيما يلي كود المصدر الكامل لميزة By Sections في Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// قسّم المستند إلى أجزاء أصغر ، في هذه الحالة ، قسّم حسب القسم.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// احفظ كل قسم كمستند منفصل.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

باستخدام هذا الرمز ، ستتمكن من تقسيم مستند Word إلى أقسام منفصلة باستخدام Aspose.Words for .NET.

الآن يمكنك العمل بسهولة مع أقسام محددة.

