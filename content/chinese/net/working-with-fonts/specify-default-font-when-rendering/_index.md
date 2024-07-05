---
title: 渲染时指定默认字体
linktitle: 渲染时指定默认字体
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 呈现文档时指定默认字体的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/specify-default-font-when-rendering/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 渲染文档时指定默认字体的过程。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何指定使用 Aspose.Words for .NET 渲染文档时要使用的默认字体。

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“YOUR DOCUMENTS DIRECTORY”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要渲染的文档
接下来，您需要使用`Document`类。请确保指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：设置默认字体
现在，您可以通过创建`FontSettings`类和设置`DefaultFontName`的财产`DefaultFontSubstitution`反对`DefaultFontSubstitution`目的`SubstitutionSettings`的`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 步骤 4：保存渲染的文档
最后，您可以使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### 使用 Aspose.Words for .NET 渲染时指定默认字体的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//如果在渲染过程中找不到此处定义的默认字体，则
//而是使用机器上最接近的字体。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 渲染文档时指定默认字体。按照本分步指南，您可以轻松设置渲染文档时使用的默认字体。Aspose.Words 提供强大而灵活的 API，用于处理文档中的字体文字。有了这些知识，您可以根据特定需求控制和自定义文档的渲染。

### 常见问题解答

#### 问：在 Aspose.Words 中转换为 PDF 时如何指定默认字体？

答：要在 Aspose.Words 中转换为 PDF 时指定默认字体，您可以使用`PdfOptions`类并设置`DefaultFontName`属性为所需字体的名称。

#### 问：转换为 PDF 时默认字体不可用怎么办？

答：如果在转换为 PDF 时指定的默认字体不可用，Aspose.Words 将使用替代字体来显示转换后的文档中的文本。这可能会导致外观与原始字体略有不同。

#### 问：我可以为其他输出格式（例如 DOCX 或 HTML）指定默认字体吗？

答：是的，您可以使用适当的转换选项并为每种格式设置相应的属性来为其他输出格式（如 DOCX 或 HTML）指定默认字体。

#### 问：如何检查 Aspose.Words 中指定的默认字体？

答：要检查 Aspose.Words 中指定的默认字体，您可以使用`DefaultFontName`的财产`PdfOptions`类并检索配置的字体的名称。

#### 问：是否可以为文档的每个部分指定不同的默认字体？

答：是的，可以使用特定于每个部分的格式化选项为文档的每个部分指定不同的默认字体。但是，这需要使用 Aspose.Words 功能对文档进行更高级的操作。