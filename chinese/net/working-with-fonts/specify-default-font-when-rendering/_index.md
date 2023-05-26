---
title: 渲染时指定默认字体
linktitle: 渲染时指定默认字体
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 呈现文档时指定默认字体的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/specify-default-font-when-rendering/
---

在本教程中，我们将逐步指导您在使用 Aspose.Words for .NET 呈现文档时指定默认字体。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将知道如何指定在使用 Aspose.Words for .NET 呈现文档时使用的默认字体。

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要呈现的文档
接下来，您需要使用`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第三步：设置默认字体
现在您可以通过创建一个实例来指定渲染时使用的默认字体`FontSettings`类和设置`DefaultFontName`的财产`DefaultFontSubstitution`反对`DefaultFontSubstitution`目的`SubstitutionSettings`的`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 第 4 步：保存呈现的文档
最后，您可以使用`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

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
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 呈现文档时指定默认字体。按照这个分步指南，您可以轻松地设置默认字体以在呈现文档时使用。 Aspose.Words 提供了强大而灵活的 API 来处理文档中的字体。有了这些知识，您就可以根据您的特定需求控制和自定义文档的呈现。