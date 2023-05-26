---
title: 类型访问
linktitle: 类型访问
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用类型化访问来操作 Aspose.Words for .NET 中的表格。
type: docs
weight: 10
url: /zh/net/working-with-node/typed-access/
---

下面是一个分步指南，用于解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 的类型化访问功能。

## 第 1 步：导入必要的引用
在您开始之前，请确保您已经导入了必要的引用以将 Aspose.Words for .NET 应用到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到您的源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 第 2 步：创建新文档
在此步骤中，我们将使用`Document`班级。

```csharp
Document doc = new Document();
```

## 第 3 步：访问部分和正文
要访问文档中包含的表格，我们必须首先访问文档的节和正文。

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## 第 4 步：快速和类型化地访问表
现在我们有了文档的主体，我们可以使用快速和类型化访问来访问主体中包含的所有表格。

```csharp
TableCollection tables = body.Tables;
```

## 第 5 步：浏览表格
通过使用`foreach`循环，我们可以循环遍历所有的表，对每个表进行特定的操作。

```csharp
foreach(Table table in tables)
{
     //快速输入表格的第一行。
     table.FirstRow?.Remove();

     //快速键入访问表的最后一行。
     table.LastRow?.Remove();
}
```

在此示例中，我们使用 Aspose.Words 提供的快速和类型化访问删除每个表的第一行和最后一行。

### 使用 Aspose.Words for .NET 进行类型化访问的示例源代码

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	//快速输入对 Body 中包含的所有 Table 子节点的访问。
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		//快速键入访问表的第一行。
		table.FirstRow?.Remove();

		//快速键入访问表的最后一行。
		table.LastRow?.Remove();
	}
            
```

这是一个完整的示例代码，用于使用 Aspose.Words for .NET 对表进行类型化访问。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

---
