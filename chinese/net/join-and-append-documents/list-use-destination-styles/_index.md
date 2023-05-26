---
title: 列表使用目标样式
linktitle: 列表使用目标样式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文档，同时保留目标文档的列表样式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/list-use-destination-styles/
---

本教程将指导您完成使用 Aspose.Words for .NET 的列表使用目标样式功能的过程。此功能允许您在使用目标文档的列表样式时加入和附加 Word 文档。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了 Aspose.Words for .NET。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 第 1 步：初始化文档目录

首先，您需要设置文档目录的路径。修改值`dataDir`变量到您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`班级。更新文件名在`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 第 3 步：将源文档设置为在目标文档之后继续

为了确保源文档的内容在目标文档结束后继续，您需要设置`SectionStart`源文档中第一节的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 第 4 步：处理列表格式

要处理列表格式，您将遍历源文档中的每个段落并检查它是否是一个列表项。如果是，您会将列表 ID 与目标文档中的现有列表进行比较。如果存在具有相同 ID 的列表，您将在源文档中创建列表的副本并更新段落的列表格式以使用复制的列表。

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## 第 5 步：将源文档附加到目标文档

现在，您可以使用`AppendDocument`的方法`Document`班级。这`ImportFormatMode.UseDestinationStyles`参数确保在附加操作期间使用目标文档的列表样式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 第 6 步：保存最终文档

最后，使用启用的列表使用目标样式功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### List Use Destination Styles using Aspose.Words for .NET 的示例源代码 

下面是使用 Aspose.Words for .NET 的 C# 中“列表使用目标样式”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//将源文档设置为在目标文档结束后直接继续。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//跟踪创建的列表。
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			//检查目标文档是否已包含具有此 ID 的列表。如果是这样，那么这可能
			//使两个列表一起运行。改为在源文档中创建列表的副本。
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				//此 ID 已存在新复制的列表，检索存储的列表，
				//并在当前段落中使用它。
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					//将此列表的副本添加到文档中并保存以供日后参考。
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				//将本段的列表设置为复制的列表。
				para.ListFormat.List = currentList;
			}
		}
	}
	//将源文档附加到目标文档的末尾。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功实现了 List Use Destination Styles 功能。最终文档将包含合并后的内容以及目标文档中的列表样式。