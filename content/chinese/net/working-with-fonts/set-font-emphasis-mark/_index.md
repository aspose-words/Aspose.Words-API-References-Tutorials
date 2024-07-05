---
title: 设置字体强调标记
linktitle: 设置字体强调标记
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-font-emphasis-mark/
---

在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。字体强调用于突出显示文本中的某些单词或短语。

## 先决条件
开始之前，请确保您拥有以下物品：
- 具备 C# 编程语言的工作知识
- 项目中安装的 .NET Aspose.Words 库

## 步骤1：定义文档目录
首先将目录路径设置为 Word 文档的位置。替换`"YOUR DOCUMENT DIRECTORY"`在代码中使用适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建并自定义文档
创建一个实例`Document`类和相关`DocumentBuilder`构建文档内容。使用`Font.EmphasisMark`属性来设置字体强调样式`EmphasisMark.UnderSolidCircle`。然后使用`Write`和`Writeln`方法`DocumentBuilder`添加具有指定字体强调的文本。

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 步骤 3：保存文档
使用`Save`方法`Document`使用适当的路径和文件名。

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### 使用 Aspose.Words for .NET 设置字体强调标记的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。尝试不同的强调样式，并使用此功能突出显示文档中的单词或短语。

### 常见问题解答

#### 问：如何使用 Aspose.Words 为 Word 文档中的特定字体添加重音符号？

答：要使用 Aspose.Words 为 Word 文档中的特定字体添加重音符号，您可以使用 API 导航到所需字体并应用适当的重音符号。这将使用所选字体为文本添加重音符号。

#### 问：是否可以使用 Aspose.Words 更改 Word 文档中重音符号的样式？

答：是的，使用 Aspose.Words，您可以更改 Word 文档中重音符号的样式。API 允许您调整样式属性（例如颜色、大小、线型等），以自定义重音符号的外观。

#### 问：如何使用 Aspose.Words 从 Word 文档中删除所有重音符号？

答：要使用 Aspose.Words 从 Word 文档中删除所有重音符号，您可以使用 API 浏览文档，检测现有重音符号并使用适当的方法将其删除。这将从文档中删除所有强调符号。

#### 问：我可以在 Word 文档中为文本的特定部分添加重音符号吗？

答：是的，您可以使用 Aspose.Words 为 Word 文档中的特定文本部分添加重音符号。您可以使用 API 选择所需的文本范围，并为该部分文本添加适当的强调符号。

#### 问：重音符号可以根据我的需要定制吗？

答：是的，可以使用 Aspose.Words 根据您的需要自定义重音符号。您可以调整重音符号的样式属性，例如颜色、大小、线型等，以匹配您的格式偏好。