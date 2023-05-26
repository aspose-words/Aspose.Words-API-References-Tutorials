---
title: 读取活动 XControl 属性
linktitle: 读取活动 XControl 属性
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 读取 Word 文档中 ActiveX 控件的属性。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 读取 Word 文档中 ActiveX 控件的属性。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第一步：文档初始化

第一步是初始化`Document`通过加载包含 ActiveX 控件的 Word 文档来创建对象。务必更换`MyDir`包含文档的目录的实际路径。

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 步骤 2：恢复 ActiveX 控件

在这一步中，我们将遍历每个`Shape`检索 ActiveX 控件并读取它们的属性。

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

### 使用 Aspose.Words for .NET 读取活动 XControl 属性的示例源代码

下面是使用 Aspose.Words for .NET 读取 ActiveX 控件属性的完整源代码：

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

