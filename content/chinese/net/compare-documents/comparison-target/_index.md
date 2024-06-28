---
title: Word文档中的比较目标
linktitle: Word文档中的比较目标
second_title: Aspose.Words 文档处理 API
description: 了解 Aspose.Words for .NET 的 Word 文档功能中的比较目标，该功能允许您比较文档并生成包含所做更改的新文档。
type: docs
weight: 10
url: /zh/net/compare-documents/comparison-target/
---
以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的 Word 文档功能中的比较目标。

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

### 使用 Aspose.Words for .NET 比较目标的示例源代码


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

//与 Microsoft Word“比较文档”对话框中的“显示更改”选项相关。
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## 结论

在本文中，我们探讨了 Aspose.Words for .NET 的 diff 目标功能。此功能允许您比较两个文档并生成包含所做更改的新文档。您可以使用这些知识来跟踪文档不同版本之间的更改。

### 常见问题解答

#### 问：在 Aspose.Words for .NET 中使用比较目标的目的是什么？

答：Aspose.Words for .NET 中的比较目标允许您比较两个文档并生成一个包含对目标文档所做更改的新文档。此功能对于跟踪文档不同版本之间所做的更改以及可视化单独文档中的差异非常有用。

#### 问：如何在 Aspose.Words for .NET 中使用比较目标？

答：要在 Aspose.Words for .NET 中使用比较目标，请按照下列步骤操作：
1. 使用 Aspose.Words 库设置您的开发环境。
2. 通过引用 Aspose.Words 将必要的程序集添加到您的项目中。
3. 使用以下命令初始化要比较的文档`Document`类或`DocumentBuilder`班级。
4. 通过创建一个来配置比较选项`CompareOptions`对象并设置属性，例如`IgnoreFormatting`和`Target`（例如。，`ComparisonTargetType.New`为比较目标）。
5. 使用`Compare`一个文档上的方法，传递另一个文档和`CompareOptions`对象作为参数。此方法将比较文档并将更改保存在第一个文档中。

#### 问：这样做的目的是什么`Target` property in the `CompareOptions` class?

答： 的`Target`财产在`CompareOptions`类允许您指定比较目标，这类似于 Microsoft Word 的“比较文档”对话框中的“显示更改”选项。目标可以设置为`ComparisonTargetType.New`显示新文档中的更改，`ComparisonTargetType.Current`显示当前文档中的更改，或`ComparisonTargetType.Formatting`仅显示格式更改。