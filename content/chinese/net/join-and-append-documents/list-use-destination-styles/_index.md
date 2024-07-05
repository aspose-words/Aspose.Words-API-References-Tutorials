---
title: 列出使用目标样式
linktitle: 列出使用目标样式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 连接和附加 Word 文档，同时保留目标文档的列表样式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/list-use-destination-styles/
---

本教程将指导您完成使用 Aspose.Words for .NET 的“使用目标样式列表”功能的过程。此功能允许您在使用目标文档的列表样式的同时加入和附加 Word 文档。

## 先决条件

开始之前，请确保您已准备好以下物品：

1. 已安装 Aspose.Words for .NET。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 步骤 1：初始化文档目录

首先，您需要设置文档目录的路径。修改`dataDir`变量为您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`类。更新`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步骤 3：将源文档设置为在目标文档之后继续

为了确保源文档的内容在目标文档结束后继续，您需要设置`SectionStart`源文档第一节的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步骤 4：处理列表格式

要处理列表格式，您将遍历源文档中的每个段落并检查它是否是列表项。如果是，您将比较列表 ID 与目标文档中的现有列表。如果存在具有相同 ID 的列表，您将在源文档中创建该列表的副本并更新段落的列表格式以使用复制的列表。

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

## 步骤 5：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.UseDestinationStyles`参数确保在附加操作期间使用目标文档的列表样式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 步骤 6：保存最终文档

最后，使用`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### 使用 Aspose.Words for .NET 的 List Use Destination Styles 的示例源代码 

以下是使用 Aspose.Words for .NET 的 C# 中的“列出使用目标样式”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//将源文档设置为在目标文档结束后直接继续。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//跟踪已创建的列表。
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			//检查目标文档是否已包含具有此 ID 的列表。如果包含，则可能
			//导致两个列表一起运行。而是在源文档中创建列表的副本。
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				//该 ID 的新复制列表已存在，请检索存储的列表，
				//并将其用于当前段落。
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					//将此列表的副本添加到文档中并存储以供日后参考。
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				//将此段落的列表设置为复制的列表。
				para.ListFormat.List = currentList;
			}
		}
	}
	//将源文档附加到目标文档的末尾。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现了列表使用目标样式功能。最终文档将包含合并的内容和来自目标文档的列表样式。