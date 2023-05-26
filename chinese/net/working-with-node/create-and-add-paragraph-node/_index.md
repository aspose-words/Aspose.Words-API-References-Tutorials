---
title: 创建和添加段落节点
linktitle: 创建和添加段落节点
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 创建段落节点并将其添加到您的 Word 文档。
type: docs
weight: 10
url: /zh/net/working-with-node/create-and-add-paragraph-node/
---

下面是一个分步指南，用于解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 创建和添加段落节点。

## 第 1 步：导入必要的引用
在您开始之前，请确保您已经导入了必要的引用以将 Aspose.Words for .NET 应用到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到您的源文件中。

```csharp
using Aspose.Words;
```

## 第 2 步：创建新文档
在此步骤中，我们将使用`Document`班级。

```csharp
Document doc = new Document();
```

## 第 3 步：创建段落节点
现在我们将使用`Paragraph`类并将文档作为参数传递。

```csharp
Paragraph para = new Paragraph(doc);
```

## 第 4 步：访问文档部分
要将段落添加到文档中，我们需要使用`LastSection`财产。

```csharp
Section section = doc.LastSection;
```

## 第 5 步：将段落节点添加到文档中
现在我们有了文档部分，我们可以使用`AppendChild`节的方法`Body`财产。

```csharp
section.Body.AppendChild(para);
```

## 第 6 步：保存文档
最后，要保存文档，您可以使用`Save`方法通过指定所需的输出格式，例如 DOCX 格式。

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### 使用 Aspose.Words for .NET 创建和添加段落节点的示例源代码

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

这是使用 Aspose.Words for .NET 创建和添加段落节点的完整代码示例。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。