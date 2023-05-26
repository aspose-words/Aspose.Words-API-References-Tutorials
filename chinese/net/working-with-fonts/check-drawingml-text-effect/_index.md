---
title: 检查 DrawingML 文本效果
linktitle: 检查 DrawingML 文本效果
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 检查 Word 文档中的 DrawingML 文本效果。
type: docs
weight: 10
url: /zh/net/working-with-fonts/check-drawingml-text-effect/
---

在本教程中，我们将带您了解如何使用 Aspose.Words Library for .NET 检查 Word 文档中的 DrawingML 文本效果。检查 DrawingML 文本效果可让您确定特定效果是否应用于部分文本。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库
- 包含 DrawingML 文本效果的 Word 文档

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档并检查文字效果
接下来，我们将加载 Word 文档并访问文档正文第一段中的运行集合（字符序列）。接下来，我们将检查是否有任何特定的 DrawingML 文本效果应用于第一次运行的字体。

```csharp
//装入文档
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

//检查 DrawingML 文本效果
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### 使用 Aspose.Words for .NET 检查 DMLText 效果的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

//一次运行可能会应用多个 Dml 文本效果。
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 检查 Word 文档中的 DrawingML 文本效果。检查 DrawingML 文本效果可让您识别应用了特定效果的文本部分。随意使用此功能来操作和分析 Word 文档中的文本效果。
