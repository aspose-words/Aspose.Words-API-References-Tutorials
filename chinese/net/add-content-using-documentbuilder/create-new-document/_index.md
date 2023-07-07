---
title: 创建新文档
linktitle: 创建新文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 创建新的 Word 文档并添加内容。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/create-new-document/
---

在本分步教程中，您将学习如何使用 Aspose.Words for .NET 从头开始创建新的 Word 文档。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够生成新文档并使用 DocumentBuilder 类向其中添加内容。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建一个新文档
首先，使用 Document 类创建一个新文档：

```csharp
Document doc = new Document();
```

## 第 2 步：向文档添加内容
接下来，使用 DocumentBuilder 对象将内容添加到文档中。使用新创建的文档初始化 DocumentBuilder：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## 第 3 步：保存文档
添加所需内容后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## 使用 Aspose.Words for .NET 创建新文档的示例源代码
以下是使用 Aspose.Words for .NET 创建新文档的完整源代码：

```csharp
Document doc = new Document();

//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## 结论

恭喜！您已成功学习如何使用 Aspose.Words for .NET 创建新的 Word 文档。通过遵循分步指南并利用提供的源代码，您现在可以以编程方式生成新文档并使用 DocumentBuilder 类向其中添加内容。

现在，您可以根据您的具体要求自信地创建和自定义 Word 文档。

### 使用 Aspose.Words for .NET 创建新文档的示例源代码：

```csharp
Document doc = new Document();

//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

请记住调整代码中的文件路径和名称，以将文档保存到系统上所需的位置。

