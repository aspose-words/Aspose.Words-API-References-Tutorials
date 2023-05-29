---
title: 插入水平标尺
linktitle: 插入水平标尺
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入水平线。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

在这个综合示例中，您将学习如何使用 Aspose.Words for .NET 将水平线插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。到本指南结束时，您将能够为文档添加水平线以进行视觉分隔和组织。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化一个 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入水平线
接下来，使用 DocumentBuilder 类的 Writeln 方法添加描述性文本，然后插入水平线：

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## 第 3 步：保存文档
插入水平线后，使用 Document 类的 Save 方法将文档保存到文件：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### 使用 Aspose.Words for .NET 插入水平线的示例源代码
下面是使用 Aspose.Words for .NET 插入水平线的完整源代码：
水平线适用于各种场景，例如划分部分、创建视觉中断或突出显示重要信息。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

请记住根据您的特定要求调整代码，并根据需要使用其他功能对其进行增强。

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 将水平线插入到 Word 文档中。按照分步指南并利用提供的源代码，您现在可以使用水平规则直观地分隔和组织您的文档。

