---
title: 克隆 Vba 模块
linktitle: 克隆 Vba 模块
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，了解如何使用 Aspose.Words for .NET 从 Word 文档克隆 VBA 模块。
type: docs
weight: 10
url: /zh/net/working-with-vba-macros/clone-vba-module/
---

在本教程中，我们将告诉您如何使用 .NET 的 Aspose.Words 库从带有宏的 Word 文档克隆 VBA 模块。克隆 VBA 模块允许您重复使用 VBA 代码或将其从一个源文档复制到另一文档。我们将逐步指导您理解并实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库
- 包含 VBA 项目以及要克隆的模块的 Word 文档

## 第1步：定义文档目录
首先，您需要将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：加载源文档
接下来，我们将加载源 Word 文档，其中包含 VBA 项目和我们要克隆的模块。

```csharp
//加载源文档
Document doc = new Document(dataDir + "VBA project.docm");
```

## 步骤 3：使用 VBA 项目创建一个新文档并克隆模块
我们将使用空的 VBA 项目创建一个新文档，并从源文档克隆指定的模块。

```csharp
//使用空的 VBA 项目创建新文档
Document destDoc = new Document { VbaProject = new VbaProject() };

//克隆模块
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## 步骤 4：保存目标文档
最后，我们将使用克隆的 VBA 模块将目标文档保存到文件中。

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### 使用 Aspose.Words for .NET 的克隆 Vba 模块的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 从带有宏的 Word 文档克隆 VBA 模块。克隆 VBA 模块使您可以轻松地在另一文档中重复使用一个源文档中的 VBA 代码。请随意使用此功能来组织和管理不同文档中的宏。
