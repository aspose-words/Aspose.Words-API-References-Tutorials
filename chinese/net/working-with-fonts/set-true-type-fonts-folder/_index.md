---
title: 设置 True Type 字体文件夹
linktitle: 设置 True Type 字体文件夹
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 渲染文档时设置 true type 字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-true-type-fonts-folder/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 渲染文档时设置 true type 字体文件夹的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何指定包含 True Type 字体的自定义文件夹，以便在使用 Aspose.Words for .NET 渲染文档时使用。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要渲染的文档
接下来，您需要使用以下命令加载要渲染的文档`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：设置 True Type 字体文件夹
现在，您可以通过创建一个实例来指定渲染时要使用的 true type 字体的文件夹`FontSettings`类并使用`SetFontsFolder()`设置字体文件夹的方法。您可以指定包含 True Type 字体的自定义文件夹。第二个参数为`SetFontsFolder()`指示是否还要搜索指定文件夹的子文件夹。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 步骤 4：保存渲染的文档
最后，您可以使用以下命令将渲染的文档保存到文件中`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### 使用 Aspose.Words for .NET 设置 True Type 字体文件夹的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//请注意，此设置将覆盖默认搜索的任何默认字体源。现在只会搜索这些文件夹
//渲染或嵌入字体时的字体。要在保留系统字体源的同时添加额外的字体源，请同时使用 FontSettings.GetFontSources 和
//相反，FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
//设置字体设置
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时设置 true type 字体文件夹。通过遵循此分步指南，您可以轻松指定包含要在渲染文档时使用的 True Type 字体的自定义文件夹。 Aspose.Words 提供了强大且灵活的 API，用于处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求渲染文档时使用的字体。

### 常见问题解答

#### 问：如何在 Aspose.Words 中配置 TrueType 字体文件夹？

答：要在 Aspose.Words 中配置 TrueType 字体文件夹，您可以使用`SetTrueTypeFontsFolder`的方法`Fonts`指定包含 TrueType 字体的文件夹位置的类。

#### 问：什么类型的字体被视为 TrueType 字体？

答：TrueType 字体是一种流行的字体格式。它们通常在 Word 文档中使用，并具有 .ttf 或 .ttc 文件扩展名。

#### 问：我可以在 Aspose.Words 中指定多个 TrueType 字体文件夹吗？

答：是的，您可以使用 Aspose.Words 中指定多个 TrueType 字体文件夹`SetTrueTypeFontsFolder`的方法`Fonts`带有文件夹位置列表的类。

#### 问：如何检查 Aspose.Words 中配置的 TrueType 字体文件夹？

答：要检查 Aspose.Words 中配置的 TrueType Fonts 文件夹，您可以使用`GetTrueTypeFontsFolder`的方法`Fonts`类来获取配置的 TrueType Fonts 文件夹的位置。

#### 问：为什么在 Aspose.Words 中配置 TrueType 字体文件夹很重要？

答：在Aspose.Words中设置TrueType字体文件夹很重要，因为它可以帮助Aspose.Words找到处理Word文档时所需的字体。这确保了文档格式和外观的一致性，即使在不同的系统中也是如此。