---
title: 收到警告通知
linktitle: 收到警告通知
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 时接收警告通知并管理文档中的任何问题或警告。
type: docs
weight: 10
url: /zh/net/working-with-fonts/receive-warning-notification/
---

在本教程中，我们将向您展示如何在使用 Aspose.Words for .NET 时获得警告通知。设置或保存文档时会发出警告。我们将逐步指导您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：上传文档并配置warning handler
使用`Document`班级。接下来，创建一个实例`HandleDocumentWarnings`处理警告的类。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## 第 3 步：更新布局并保存文档
通过调用更新文档布局`UpdatePageLayout()`方法。这将触发警告（如果有）。然后保存文档。

```csharp
doc.UpdatePageLayout();
doc.Save(dataDir + "WorkingWithFonts.ReceiveWarningNotification.pdf");
```

### 使用 Aspose.Words for .NET 接收警告通知的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
//当您调用 UpdatePageLayout 时，文档会在内存中呈现。渲染期间出现的任何警告
//存储直到文档保存，然后发送到适当的 WarningCallback。
doc.UpdatePageLayout();
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
//即使文档之前已呈现，任何保存警告都会在文档保存期间通知用户。
doc.Save(dataDir + "WorkingWithFonts.ReceiveWarningNotification.pdf");

```

## 结论
在本教程中，您学习了如何在使用 Aspose.Words for .NET 时接收警告通知。设置或保存文档时会发出警告。使用此功能可收到与文档相关的任何问题或警告的通知。
