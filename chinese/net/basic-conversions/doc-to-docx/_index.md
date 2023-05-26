---
title: 文档到文档
linktitle: 文档到文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 .doc 格式转换为 Docx 格式。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/doc-to-docx/
---

在本教程中，我们将逐步引导您使用 Aspose.Words for .NET 将 .doc 格式的 Word 文档转换为 Docx 格式。我们将解释提供的 C# 源代码，并指导您如何在自己的项目中实施它。

首先，确保您在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第一步：搭建开发环境

在开始编码之前，请确保您拥有合适的开发环境。打开 Visual Studio 或您首选的 C# IDE 并创建一个新项目。

## 第 2 步：添加引用和导入命名空间

要使用 Aspose.Words for .NET，您需要在项目中添加对库的引用。右键单击项目中的 References 文件夹，选择“添加引用”，然后浏览到安装 Aspose.Words for .NET 库的位置。选择适当的版本并单击“确定”以添加引用。

接下来，在 C# 文件的顶部导入必要的命名空间：

```csharp
using Aspose.Words;
```

## 第三步：初始化文档对象

在此步骤中，您将初始化`Document`带有 .doc 格式源文档路径的对象。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在的实际目录路径，以及`"Document.doc"`与您的源文档的名称。这是代码片段：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## 第 4 步：将文档转换为 Docx 格式

现在你已经初始化了`Document`对象，您可以继续转换过程。 Aspose.Words for .NET 提供了各种自定义选项和设置，但对于基本转换，不需要额外的参数。

## 第 5 步：保存转换后的文档

要将转换后的文档保存为 Docx 格式，您需要调用`Save`上的方法`Document`目的。提供输出文档的路径和文件名。在这个例子中，我们将它保存为`"BaseConversions.DocToDocx.docx"`.这是代码片段：

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 .doc 格式的 Word 文档转换为 Docx 格式。

### 使用 Aspose.Words for .NET 的 Doc To Docx 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。




