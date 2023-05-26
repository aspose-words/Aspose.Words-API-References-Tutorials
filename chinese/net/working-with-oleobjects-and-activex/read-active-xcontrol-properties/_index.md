---
title: قراءة خصائص Active XControl
linktitle: قراءة خصائص Active XControl
second_title: Aspose.Words لمراجع .NET API
description: اقرأ خصائص عناصر تحكم ActiveX في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

في هذا الدليل التفصيلي ، سنوضح لك كيفية قراءة خصائص عناصر تحكم ActiveX في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تهيئة المستند

 الخطوة الأولى هي تهيئة ملف`Document` الكائن عن طريق تحميل مستند Word الذي يحتوي على عناصر تحكم ActiveX. تأكد من استبدال`MyDir` بالمسار الفعلي للدليل الذي يحتوي على المستند.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## الخطوة 2: استرداد عناصر تحكم ActiveX

 في هذه الخطوة ، سوف نكرر كل منها`Shape` من المستند لاسترداد عناصر تحكم ActiveX وقراءة خصائصها.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### مثال على شفرة المصدر لـ Read Active XControl Properties باستخدام Aspose.Words for .NET

فيما يلي التعليمات البرمجية المصدر الكاملة لقراءة خصائص عناصر تحكم ActiveX باستخدام Aspose.Words for .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

