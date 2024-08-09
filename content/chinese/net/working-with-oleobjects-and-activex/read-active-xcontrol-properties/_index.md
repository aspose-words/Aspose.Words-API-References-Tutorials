---
title: 从 Word 文件读取 Active XControl 属性
linktitle: 从 Word 文件读取 Active XControl 属性
second_title: Aspose.Words 文档处理 API
description: 通过分步指南了解如何使用 Aspose.Words for .NET 从 Word 文件中读取 ActiveX 控件属性。增强您的文档自动化技能。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## 介绍

在当今的数字时代，自动化是提高生产力的关键。如果您正在使用包含 ActiveX 控件的 Word 文档，则可能需要读取它们的属性以用于各种目的。ActiveX 控件（例如复选框和按钮）可以保存重要数据。使用 Aspose.Words for .NET，您可以高效地以编程方式提取和操作这些数据。

## 先决条件

在开始之前，请确保您已准备好以下物品：

1.  Aspose.Words for .NET 库：您可以从以下位置下载[这里](https://releases.aspose.com/words/net/).
2. Visual Studio 或任何 C# IDE：编写和执行您的代码。
3. 带有 ActiveX 控件的 Word 文档：例如“ActiveX controls.docx”。
4. C# 基础知识：需要熟悉 C# 编程才能继续学习。

## 导入命名空间

首先，让我们导入使用 Aspose.Words for .NET 所需的命名空间。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## 步骤 1：加载 Word 文档

首先，您需要加载包含 ActiveX 控件的 Word 文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## 步骤 2：初始化字符串以保存属性

接下来，初始化一个空字符串来存储 ActiveX 控件的属性。

```csharp
string properties = "";
```

## 步骤 3：遍历文档中的形状

我们需要遍历文档中的所有形状来找到 ActiveX 控件。

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        //处理 ActiveX 控件
    }
}
```

## 步骤 4：从 ActiveX 控件中提取属性

在循环中，检查控件是否为 Forms2OleControl。如果是，则对其进行强制转换并提取属性。

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## 步骤 5：统计 ActiveX 控件总数

遍历所有形状后，计算找到的 ActiveX 控件的总数。

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## 步骤 6：显示属性

最后，将提取的属性打印到控制台。

```csharp
Console.WriteLine("\n" + properties);
```

## 结论

就这样！您已成功学会了如何使用 Aspose.Words for .NET 从 Word 文档中读取 ActiveX 控件属性。本教程涵盖了加载文档、遍历形状以及从 ActiveX 控件中提取属性。通过遵循这些步骤，您可以自动从 Word 文档中提取重要数据，从而提高工作流程效率。

## 常见问题解答

### Word 文档中的 ActiveX 控件是什么？
ActiveX 控件是嵌入在 Word 文档中的交互式对象，例如复选框、按钮和文本字段，用于创建表单和自动执行任务。

### 我可以使用 Aspose.Words for .NET 修改 ActiveX 控件的属性吗？
是的，Aspose.Words for .NET 允许您以编程方式修改 ActiveX 控件的属性。

### Aspose.Words for .NET 可以免费使用吗？
 Aspose.Words for .NET 提供免费试用，但您需要购买许可证才能继续使用。您可以免费试用[这里](https://releases.aspose.com/).

### 除了 C# 之外，我可以将 Aspose.Words for .NET 与其他 .NET 语言一起使用吗？
是的，Aspose.Words for .NET 可以与任何 .NET 语言一起使用，包括 VB.NET 和 F#。

### 在哪里可以找到有关 Aspose.Words for .NET 的更多文档？
您可以找到详细的文档[这里](https://reference.aspose.com/words/net/).