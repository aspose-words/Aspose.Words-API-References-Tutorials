---
title: 更新上次保存时间属性
linktitle: 更新上次保存时间属性
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的上次保存时间属性。请遵循我们详细的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
## 介绍

有没有想过如何以编程方式跟踪 Word 文档中的上次保存时间属性？如果您要处理多个文档并需要维护其元数据，则更新上次保存时间属性会非常方便。今天，我将使用 Aspose.Words for .NET 引导您完成此过程。所以，系好安全带，让我们开始吧！

## 先决条件

在我们进入分步指南之前，您需要准备一些东西：

1.  Aspose.Words for .NET：确保您已安装 Aspose.Words for .NET。如果没有，您可以[点击下载](https://releases.aspose.com/words/net/).
2. 开发环境：像 Visual Studio 这样的开发环境。
3. C# 基础知识：了解 C# 编程的基础知识将会有所帮助。

## 导入命名空间

首先，确保将必要的命名空间导入到您的项目中。这将允许您访问操作 Word 文档所需的类和方法。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

现在，让我们将这个过程分解成几个简单的步骤。每个步骤都将指导您完成更新 Word 文档中上次保存的时间属性的过程。

## 步骤 1：设置文档目录

首先，您需要指定文档目录的路径。这是您现有文档的存储位置，也是更新文档的保存位置。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与您的目录的实际路径一致。

## 第 2 步：加载 Word 文档

接下来，加载要更新的 Word 文档。您可以通过创建`Document`类并传递文档的路径。

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

确保名为`Document.docx`存在于指定目录中。

## 步骤 3：配置保存选项

现在，创建一个实例`OoxmlSaveOptions`类。此类允许您指定以 Office Open XML (OOXML) 格式保存文档的选项。在这里，您将设置`UpdateLastSavedTimeProperty`到`true`.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions
{
    UpdateLastSavedTimeProperty = true
};
```

这告诉 Aspose.Words 更新文档的最后保存时间属性。

## 步骤 4：保存更新后的文档

最后，使用`Save`方法`Document`类，传递您想要保存更新文档的路径和保存选项。

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

这将使用更新的上次保存时间属性来保存文档。

## 结论

就这样！按照这些步骤，您可以使用 Aspose.Words for .NET 轻松更新 Word 文档的上次保存时间属性。这对于维护文档中的准确元数据特别有用，这对于文档管理系统和其他各种应用程序至关重要。

## 常见问题解答

### 什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个功能强大的库，用于在 .NET 应用程序中创建、编辑和转换 Word 文档。

### 为什么我应该更新最后保存的时间属性？
更新最后保存的时间属性有助于维护准确的元数据，这对于文档跟踪和管理至关重要。

### 我可以使用 Aspose.Words for .NET 更新其他属性吗？
是的，Aspose.Words for .NET 允许您更新各种文档属性，例如标题、作者和主题。

### Aspose.Words for .NET 免费吗？
 Aspose.Words for .NET 提供免费试用，但要获得完整功能，需要许可证。您可以获取许可证[这里](https://purchase.aspose.com/buy).

### 在哪里可以找到有关 Aspose.Words for .NET 的更多教程？
您可以找到更多教程和文档[这里](https://reference.aspose.com/words/net/).
