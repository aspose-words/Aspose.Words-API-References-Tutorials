---
title: تعداد العقد الفرعية
linktitle: تعداد العقد الفرعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعداد العقد الفرعية في فقرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-node/enumerate-child-nodes/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه والتي توضح كيفية تعداد العقد الفرعية باستخدام Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## الخطوة 2: قم بإنشاء مستند جديد
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 3: الوصول إلى الفقرة والعقد التابعة لها
 لتعداد العقد الفرعية للفقرة ، نحتاج أولاً إلى الوصول إلى الفقرة نفسها. استخدم ال`GetChild` الطريقة مع`Paragraph` نوع العقدة للحصول على الفقرة الأولى من المستند.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

بعد ذلك ، نسترجع مجموعة العقد الفرعية للفقرة باستخدام الامتداد`ChildNodes` ملكية.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## الخطوة 4: تصفح العقد الفرعية
 الآن بعد أن أصبح لدينا مجموعة العقد الفرعية ، يمكننا المرور عبرها باستخدام ملف`foreach` حلقة. نتحقق من نوع كل عقدة فرعية ونجري عمليات محددة بناءً على النوع.

```csharp
foreach (Node child in children)
{
     // يمكن أن تحتوي الفقرة على توابع من أنواع مختلفة مثل المسارات والأشكال وغيرها.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 في هذا المثال ، نتحقق مما إذا كانت العقدة الفرعية من النوع`Run` (على سبيل المثال جزء من النص). إذا كان الأمر كذلك ، نقوم بتحويل العقدة إلى`Run` وعرض النص باستخدام`run.Text`.

## مثال على شفرة المصدر لتعداد العقد الفرعية باستخدام Aspose.Words for .NET


```csharp
	Document doc = new Document();
	Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

	NodeCollection children = paragraph.ChildNodes;
	foreach (Node child in children)
	{
		// قد تحتوي الفقرة على أطفال من أنواع مختلفة مثل الأشواط والأشكال وغيرها.
		if (child.NodeType == NodeType.Run)
		{
			Run run = (Run) child;
			Console.WriteLine(run.Text);
		}
	}
            
```

هذا مثال رمز كامل لتعداد العقد الفرعية للفقرة باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع

