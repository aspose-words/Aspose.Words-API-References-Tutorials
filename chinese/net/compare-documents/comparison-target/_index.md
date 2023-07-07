---
title: 比较目标
linktitle: 比较目标
second_title: Aspose.Words for .NET API 参考
description: 了解 Aspose.Words for .NET 的比较目标功能，该功能允许您比较文档并生成包含所做更改的新文档。
type: docs
weight: 10
url: /zh/net/compare-documents/comparison-target/
---

以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的比较目标功能。

## 第 1 步：简介

Aspose.Words for .NET 的比较目标功能允许您比较两个文档并生成一个包含对目标文档所做更改的新文档。这对于跟踪文档的不同版本之间所做的更改非常有用。

## 第2步：设置环境

在开始之前，您需要设置开发环境以使用 Aspose.Words for .NET。确保您已安装 Aspose.Words 库并拥有合适的 C# 项目来嵌入代码。

## 第 3 步：添加所需的程序集

要使用 Aspose.Words for .NET 的比较目标功能，您必须将必要的程序集添加到项目中。确保您的项目中有对 Aspose.Words 的正确引用。

```csharp
using Aspose.Words;
```

## 第四步：文档初始化

在这一步中，我们将初始化两个文档以进行比较。您必须指定文档所在的目录路径以及源文档的名称。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//初始化要比较的文档 A。
Document docA = new Document(dataDir + "DocumentA.docx");

//克隆文档 A 以创建文档 B 的相同副本。
Document docB = docA.Clone();
```

## 第 5 步：配置比较选项

在此步骤中，我们将配置比较选项以指定比较的行为。选项包括忽略格式的功能以及比较目标，即 Microsoft Word 的“比较文档”对话框中的“显示更改”选项。

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## 第六步：文档比较

现在我们将比较文档并在新文档中生成结果。

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

这`Compare`方法将文档 A 与文档 B 进行比较，并将更改保存到文档 A。您可以指定用户名和比较日期以供参考。

### 使用 Aspose.Words for .NET 的比较目标的示例源代码


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

//与 Microsoft Word“比较文档”对话框中的“显示更改”选项相关。
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## 结论

在本文中，我们探讨了 Aspose.Words for .NET 的 diff 目标功能。此功能允许您比较两个文档并生成包含所做更改的新文档。您可以使用这些知识来跟踪文档不同版本之间的更改。

