---
title: 负载链
linktitle: 负载链
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 加载 CHM 文件。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/load-chm/
---

在 C# 应用程序中使用 HTML 帮助 (CHM) 文件时，能够正确加载它们非常重要。使用适用于 .NET 的 Aspose.Words 库，您可以使用适当的加载选项轻松加载 CHM 文件。在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET C# 源代码使用 LoadOptions 加载选项加载 CHM 文件。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个强大的库，可以在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是为我们的 CHM 文件配置加载选项。使用 LoadOptions 类指定加载参数。在我们的例子中，我们需要将 Encoding 属性设置为 CHM 文件的适当编码，通常是“windows-1251”。方法如下：

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

我们创建一个新的 LoadOptions 对象并将 Encoding 属性设置为 CHM 文件的“windows-1251”编码。

## 加载 CHM 文件

现在我们已经配置了加载选项，我们可以使用 Document 类加载 CHM 文件并指定加载选项。这是一个例子：

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的 CHM 文件“HTML help.chm”。

### 使用 Aspose.Words for .NET 的具有“Load Chm”功能的 LoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“Load Chm”功能配置加载选项
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

//使用指定选项加载 CHM 文件
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库加载 CHM 文件。按照提供的步骤并使用提供的 C# 源代码，您可以轻松地将此功能应用到您的 C# 应用程序中。正确加载 CHM 文件对于使用 Aspose.Words 有效地操作和转换它们至关重要。