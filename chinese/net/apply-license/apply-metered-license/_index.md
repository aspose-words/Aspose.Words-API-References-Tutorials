---
title: 应用计量许可证
linktitle: 应用计量许可证
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 应用计量许可证。
type: docs
weight: 10
url: /zh/net/apply-license/apply-metered-license/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 应用计量许可证。我们将通过详细的分步说明指导您完成整个过程，并提供必要的 C# 代码片段。在本指南结束时，您将能够应用计量许可证并利用 Aspose.Words 的高级功能来满足您的文档处理需求。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。
- 计量许可的有效凭据。 

## 第 1 步：导入所需的命名空间
首先，在您的 C# 代码中导入必要的命名空间。这些名称空间包含使用 Aspose.Words 所需的类和方法。

```csharp
using Aspose.Words;
```

## 第 2 步：设置计量许可证密钥
接下来，您需要使用 Metered 类的 SetMeteredKey 方法设置计量许可证密钥。提供您的计量公钥和私钥作为此方法的参数。

```csharp
try
{
    Metered metered = new Metered();
    metered.SetMeteredKey("*", "*");
}
catch (Exception e)
{
    Console.WriteLine("\nThere was an error setting the license: " + e.Message);
}
```

## 第 3 步：加载和处理文档
现在您已经设置了计量许可证，您可以使用 Aspose.Words 加载和处理文档。在下面的代码片段中，我们加载了一个名为“Document.docx”的文档并执行了打印页数的简单操作。

```csharp
try
{
    Document doc = new Document(MyDir + "Document.docx");
    Console.WriteLine(doc.PageCount);
}
catch (Exception e)
{
    Console.WriteLine("\nThere was an error setting the license: " + e.Message);
}
```

### 使用 Aspose.Words for .NET 应用计量许可证的示例源代码
以下是使用 Aspose.Words for .NET 应用计量许可证的完整源代码：

```csharp
try
{
    Metered metered = new Metered();
    metered.SetMeteredKey("*", "*");

    Document doc = new Document(MyDir + "Document.docx");

    Console.WriteLine(doc.PageCount);
}
catch (Exception e)
{
    Console.WriteLine("\nThere was an error setting the license: " + e.Message);
}
```

## 结论
恭喜！您已成功了解如何使用 Aspose.Words for .NET 应用计量许可证。按照分步指南并利用提供的源代码，您现在可以利用 Aspose.Words 的高级功能来完成您的文档处理任务。

现在您可以自信地设置计量许可、加载和处理文档，并利用 Aspose.Words 的全部潜力以编程方式创建、修改和操作 Word 文档。