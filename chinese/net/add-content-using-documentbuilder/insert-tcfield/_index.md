---
title: 插入 TCField
linktitle: 插入 TCField
second_title: Aspose.Words for .NET API 参考
description: 在此分步指南中，了解如何使用 C# 和 Aspose.Words for .NET 在 Word 文档中插入和操作 TCFields。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-tcfield/
---

在本例中，我们将指导您完成使用 Aspose.Words for .NET 的 Insert TCField 功能的过程。 TCField 表示 Word 文档中的目录条目。我们将提供 C# 源代码的分步说明，以及 markdown 格式的预期输出。让我们开始吧！

## 第 1 步：初始化文档和文档生成器

首先，我们需要初始化文档和文档生成器。文档生成器是 Aspose.Words for .NET 提供的一个强大的工具，它允许我们以编程方式构建和操作 Word 文档。以下是您的操作方法：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入 TCField

接下来，我们将使用`InsertField`方法。 TCField 表示具有指定条目文本的目录条目。这是一个例子：

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

上面的代码将在文档中插入一个带有条目文本“Entry Text”的 TCField。

## 第 3 步：保存文档

插入 TCField 后，我们可以使用`Save`方法。确保为输出文档提供所需的路径和文件名。这是一个例子：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

上面的代码会将带有TCField 的文档保存到指定的目录中。

## 输出降价格式

当代码成功执行时，输出文档将包含一个带有指定条目文本的目录条目。 TCField 在 Word 文档中表示为一个字段，生成的 markdown 格式将取决于文档的处理方式。

请注意，输出文档不是直接为 markdown 格式，而是 Word 格式。但是，当您使用适当的工具或库将 Word 文档转换为 markdown 时，TCField 将被相应地处理。

### 使用 Aspose.Words for .NET 插入 TCField 的示例源代码

下面是使用 Aspose.Words for .NET 插入 TCField 的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertField("TC \"Entry Text\" \\f t");

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
			
```

随意根据您的要求修改代码并探索 Aspose.Words for .NET 提供的其他功能。

就是这样！您已经成功学习了如何使用 Aspose.Words for .NET 插入 TCField。

