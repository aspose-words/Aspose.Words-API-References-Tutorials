---
title: 设置字体回退设置
linktitle: 设置字体回退设置
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中设置字体替换设置以及如何在 Word 文档中自定义字体替换。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-font-fallback-settings/
---
在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中设置字体替换设置。字体替换设置允许您指定在指定字体不可用时要使用的替换字体。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载字体替换设置
创建一个实例`FontSettings`上课并使用`Load`从 XML 文件加载字体覆盖设置的方法。指定的 XML 文件必须包含要使用的字体替换规则。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## 第 3 步：应用字体替换设置
将字体替换设置与文档相关联，方法是将它们分配给文档的`FontSettings`财产。

```csharp
doc.FontSettings = fontSettings;
```

## 第 4 步：保存文档
使用`Save`的方法`Document`使用适当的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### 使用 Aspose.Words for .NET 设置字体回退设置的示例源代码 
```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 在 Word 文档中设置字体替换设置。尝试不同的字体替换规则以确保您的文档看起来一致，即使指定的字体不可用也是如此。
