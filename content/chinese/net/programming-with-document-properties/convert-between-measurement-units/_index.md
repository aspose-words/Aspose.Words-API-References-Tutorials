---
title: 测量单位之间的转换
linktitle: 测量单位之间的转换
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 在文档中的测量单位之间进行转换的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/convert-between-measurement-units/
---

在本教程中，我们将引导您完成 C# 源代码，以便使用 Aspose.Words for .NET 在测量单位之间进行转换。此功能允许您以不同的测量单位指定边距、页眉和页脚距离等。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：创建文档和构造函数

在此步骤中，我们将创建一个新文档并初始化构造函数。使用以下代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：配置计量单位

现在我们将转换不同测量单位的边距、页眉和页脚距离等值。使用以下代码指定特定测量单位的值：

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

这段代码使用了`ConvertUtil`Aspose.Words 类将指定值转换为英寸（`InchToPoint` ）。您还可以使用其他可用的转换方法`ConvertUtil`类将值转换为其他测量单位。

### 使用 Aspose.Words for .NET 在测量单位之间转换的示例源代码

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

您现在已经了解了如何使用 Aspose.Words for .NET 在文档中指定边距、页眉和页脚距离等时在测量单位之间进行转换。通过遵循本教程中提供的分步指南，您可以轻松地在自己的文档中指定所需测量单位的值。