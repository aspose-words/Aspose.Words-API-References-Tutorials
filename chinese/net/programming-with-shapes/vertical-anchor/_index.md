---
title: 垂直锚
linktitle: 垂直锚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 中的垂直锚点功能在文档中垂直定位形状。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/vertical-anchor/
---

本教程解释了如何使用 Aspose.Words for .NET 中的垂直锚点功能在文档中垂直定位形状。通过设置形状的垂直锚点属性，您可以控制其相对于文本或页面的垂直对齐方式。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入和配置形状
使用`InsertShape`的方法`DocumentBuilder`目的。为形状设置所需的尺寸。

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## 第 4 步：设置垂直锚点
设置形状的垂直锚点属性以控制其垂直对齐方式。在此示例中，我们将其设置为“底部”以将形状锚定在文本或页面的底部。

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## 第 5 步：向形状添加内容
使用`MoveTo`的方法`DocumentBuilder`对象将光标移动到形状的第一段。然后，使用`Write`向形状添加内容的方法。

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 第 6 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithShapes.VerticalAnchor.docx”。

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### 使用 Aspose.Words for .NET 的垂直锚点示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 中的垂直锚点功能在文档中垂直定位形状。