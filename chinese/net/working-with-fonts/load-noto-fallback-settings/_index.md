---
title: 加载 Noto 回退设置
linktitle: 加载 Noto 回退设置
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 将 Noto 覆盖参数加载到 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fonts/load-noto-fallback-settings/
---
在本教程中，我们将带您了解如何使用 Aspose.Words Library for .NET 将 Noto 字体替换设置加载到 Word 文档中。 Noto 字体替换设置允许您在显示或打印文档时管理字体替换。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

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

## 第 2 步：加载文档并配置字体替换设置
接下来，我们将使用`Document`使用类和配置字体覆盖设置`FontSettings`班级。我们将使用`LoadNotoFallbackSettings()`方法。

```csharp
//加载文档并配置字体替换设置
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## 第 3 步：保存文档
最后，我们将保存应用了 Noto 字体替换设置的文档。

```csharp
//保存文件
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### 使用 Aspose.Words for .NET 的 Noto 回退设置示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 在 Word 文档中加载 Noto 字体替换设置。 Noto 字体替换设置允许您管理字体替换以改进文档的显示和打印。随意使用此功能根据您的需要自定义字体替换。