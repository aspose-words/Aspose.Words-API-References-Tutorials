---
title: 设置字体文件夹默认实例
linktitle: 设置字体文件夹默认实例
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 呈现文档时设置默认字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-default-instance/
---

在本教程中，我们将逐步指导您在使用 Aspose.Words for .NET 渲染文档时设置默认字体文件夹。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何设置在使用 Aspose.Words for .NET 呈现文档时使用的默认字体文件夹。

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：设置默认字体文件夹
然后你可以使用设置默认字体文件夹`FontSettings.DefaultInstance`类和`SetFontsFolder()`方法。指定要用作默认文件夹的字体文件夹的路径。

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## 第 3 步：加载要渲染的文档
现在您可以加载文档以使用`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第 4 步：保存呈现的文档
最后，您可以使用`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### 使用 Aspose.Words for .NET 设置字体文件夹默认实例的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时设置默认字体文件夹。按照此分步指南，您可以轻松指定在呈现文档时将哪个字体文件夹用作默认文件夹。 Aspose.Words 提供了强大而灵活的 API 来处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求呈现文档时使用的字体源。