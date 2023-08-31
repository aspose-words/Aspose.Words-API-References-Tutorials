---
title: 资源 Steam 字体源示例
linktitle: 资源 Steam 字体源示例
second_title: Aspose.Words 文档处理 API
description: 了解如何使用资源流字体源将自定义字体加载到 Aspose.Words for .NET 中。
type: docs
weight: 10
url: /zh/net/working-with-fonts/resource-steam-font-source-example/
---

在本教程中，我们将引导您了解如何将资源流字体源与 Aspose.Words for .NET 结合使用。此字体源允许您从资源流加载字体，当您想要将自定义字体合并到应用程序中时，这非常有用。

## 先决条件
开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第1步：定义文档目录
首先，您需要将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤2：上传文档并设置资源流字体源
接下来，我们将使用以下命令加载文档`Document`类并使用以下命令设置资源流字体源`FontSettings.DefaultInstance.SetFontsSources()`班级。这将允许 Aspose.Words 在资源流中查找字体。

```csharp
//加载文档并设置资源流字体源
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## 步骤 3：保存文档
最后，我们将保存文档。字体将从指定的资源流加载并嵌入到文档中。

```csharp
//保存文档
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### 使用 Aspose.Words for .NET 的 Resource Steam 字体源示例的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 结论
在本教程中，您学习了如何将资源流字体源与 Aspose.Words for .NET 结合使用。此功能允许您从资源源加载字体，当您想要将自定义字体嵌入到文档中时，这非常有用。尝试不同的字体并探索 Aspose.Words 为字体管理提供的可能性。

### 常见问题解答

#### 问：如何将资源流中的字体加载到 Aspose.Words 中？

答：要从 Aspose.Words 中的资源流加载字体，您可以使用`FontSettings`类和`SetFontsSources`方法使用资源流指定字体源。这允许直接从资源流而不是从物理文件加载字体。

#### 问：在 Aspose.Words 中使用资源流指定字体源有什么好处？

A：使用资源流指定字体源有几个优点：
- 允许您从应用程序内置的资源加载字体，从而轻松部署和分发文档。
- 提高字体管理的灵活性，因为您可以根据需要从不同的资源流加载字体。

#### 问：如何将字体添加到 .NET 应用程序的资源流中？

答：要将字体添加到 .NET 应用程序的资源流中，您必须将字体文件嵌入到项目资源中。然后，您可以使用特定于您的开发平台的方法访问这些字体文件（例如，`GetManifestResourceStream`使用`System.Reflection`命名空间）。

#### 问：是否可以将不同资源流中的多种字体加载到单个 Aspose.Words 文档中？

答：是的，完全可以将不同资源流中的多种字体加载到单个 Aspose.Words 文档中。您可以使用指定多个字体源`SetFontsSources`的方法`FontSettings`类，为每种字体提供适当的资源流。

#### 问：我可以使用哪些类型的资源流将字体加载到 Aspose.Words 中？

答：您可以使用不同类型的资源流将字体加载到 Aspose.Words 中，例如 .NET 应用程序中内置的资源流、来自外部文件的资源流、来自数据库的资源流等。请务必提供适当的资源流。资源流基于您的设置和需求。