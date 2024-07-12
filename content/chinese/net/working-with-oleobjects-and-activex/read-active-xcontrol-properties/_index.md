---
title: 从 Word 文件读取 Active XControl 属性
linktitle: 从 Word 文件读取 Active XControl 属性
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 读取 Word 文件中 ActiveX 控件的属性。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 读取 Word 文件中 ActiveX 控件的属性。我们将为您提供完整的源代码并向您展示如何格式化 markdown 输出。

## 步骤 1：文档初始化

第一步是初始化`Document`通过加载包含 ActiveX 控件的 Word 文档来替换对象。务必替换`MyDir`包含文档的目录的实际路径。

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 步骤 2：恢复 ActiveX 控件

在此步骤中，我们将迭代每个`Shape`文档来检索 ActiveX 控件并读取其属性。

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

### 使用 Aspose.Words for .NET 读取 Active XControl 属性的示例源代码

以下是使用 Aspose.Words for .NET 读取 ActiveX 控件属性的完整源代码：

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

## 结论

本指南向您展示了如何使用 Aspose.Words for .NET 读取 Word 文件中 ActiveX 控件的属性。按照所述步骤，您可以初始化文档、检索 ActiveX 控件并读取其属性。使用提供的示例代码作为起点，并根据您的特定需求进行自定义。

读取 ActiveX 控件的属性可让您从包含这些控件的 Word 文件中提取重要信息。Aspose.Words for .NET 提供了使用 ActiveX 控件进行文字处理和自动化文档处理的强大功能。

### 常见问题解答

#### 问：读取 Word 文件中 ActiveX 控件的属性的第一步是什么？

答：第一步是初始化`Document`通过加载包含 ActiveX 控件的 Word 文档来替换对象。务必替换`MyDir`包含文档的目录的实际路径。

#### 问：如何将 ActiveX 控件放入文档中？

答：要检索 ActiveX 控件，您需要遍历每个`Shape`并检查它是否是 ActiveX 控件。使用`OleFormat`的財產`Shape`访问`OleControl`对象并检索必要的属性。

#### 问：我可以读取 ActiveX 控件的哪些属性？

答：您可以读取 ActiveX 控件的各种属性，例如标题、值、启用或禁用状态、类型以及与控件关联的子节点。

#### 问：如何获取文档中 ActiveX 控件的总数？

答：要获取文档中 ActiveX 控件的总数，可以使用`GetChildNodes`方法`Document`指定对象`NodeType.Shape`类型并包括子节点。