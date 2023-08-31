---
title: 检查DrawingML文本效果
linktitle: 检查DrawingML文本效果
second_title: Aspose.Words 文档处理 API
description: 在本教程中，了解如何使用 Aspose.Words for .NET 检查 Word 文档中的 DrawingML 文本效果。
type: docs
weight: 10
url: /zh/net/working-with-fonts/check-drawingml-text-effect/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words Library for .NET 检查 Word 文档中的 DrawingML 文本效果。通过检查 DrawingML 文本效果，您可以确定是否将特定效果应用于部分文本。我们将逐步指导您理解并实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库
- 包含 DrawingML 文本效果的 Word 文档

## 第1步：定义文档目录
首先，您需要将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：加载文档并检查文字效果
接下来，我们将加载 Word 文档并访问文档正文第一段中的运行（字符序列）集合。接下来，我们将检查是否有任何特定的 DrawingML 文本效果应用于第一次运行的字体。

```csharp
//加载文档
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

//检查DrawingML文本效果
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

//一次运行可能会应用多种 Dml 文本效果。
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 检查 Word 文档中的 DrawingML 文本效果。通过检查 DrawingML 文本效果，您可以识别应用了特定效果的文本部分。请随意使用此功能来操作和分析 Word 文档中的文本效果。

### 常见问题解答

#### 问：如何使用 Aspose.Words 访问 Word 文档中的 DrawingML 文本效果？

答：通过 Aspose.Words，您可以使用提供的 API 访问 Word 文档中的 DrawingML 文本效果。您可以浏览文本元素并检查文本效果的特定属性，例如颜色、大小等。

#### 问：Word 文档中常用的 DrawingML 文本效果有哪些类型？

答：Word 文档中常用的 DrawingML 文本效果类型包括阴影、反射、发光、渐变等。这些效果可用于改善文本的外观和格式。

#### 问：如何检查 Word 文档中 DrawingML 文本效果的颜色？

答：要检查Word文档中DrawingML文本效果的颜色，您可以使用Aspose.Words提供的方法来访问文本效果的颜色属性。这样您就可以获得用于特定文本效果的颜色。

#### 问：是否可以检查包含多个节的Word文档中的文本效果？

答：是的，Aspose.Words 允许检查包含多个部分的 Word 文档中的文本效果。您可以浏览文档的每个部分并单独访问每个部分的文本效果。

#### 问：如何检查 Word 文档中 DrawingML 文本效果的不透明度？

答：要检查Word文档中DrawingML文本效果的不透明度，您可以使用Aspose.Words提供的方法来访问文本效果的不透明度属性。这将允许您获取应用于特定文本效果的不透明度值。