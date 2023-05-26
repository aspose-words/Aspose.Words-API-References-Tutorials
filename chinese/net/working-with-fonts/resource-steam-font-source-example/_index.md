---
title: 资源 Steam 字体源示例
linktitle: 资源 Steam 字体源示例
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Resource Stream Font Source 将自定义字体加载到 Aspose.Words for .NET 中。
type: docs
weight: 10
url: /zh/net/working-with-fonts/resource-steam-font-source-example/
---

在本教程中，我们将向您介绍如何将 Resource Flow Font Source 与 Aspose.Words for .NET 一起使用。此字体源允许您从资源流加载字体，这在您想要将自定义字体合并到您的应用程序中时非常有用。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：上传文档并设置资源流字体来源
接下来，我们将使用`Document`类并使用设置资源流字体源`FontSettings.DefaultInstance.SetFontsSources()`班级。这将允许 Aspose.Words 在资源流中找到字体。

```csharp
//加载文档并设置资源流字体源
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## 第 3 步：保存文档
最后，我们将保存文档。字体将从指定的资源流中加载并嵌入到文档中。

```csharp
//保存文件
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### 使用 Aspose.Words for .NET 的 Resource Steam Font Source Example 的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 结论
在本教程中，您学习了如何将 Resource Flow Font Source 与 Aspose.Words for .NET 一起使用。此功能允许您从资源提要加载字体，这在您想要将自定义字体嵌入到文档中时非常有用。尝试不同的字体并探索 Aspose.Words 为字体管理提供的可能性。
