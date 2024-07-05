---
title: 垂直锚
linktitle: 垂直锚
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 中的垂直锚点功能在文档内垂直定位形状。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/vertical-anchor/
---

本教程介绍如何使用 Aspose.Words for .NET 中的垂直锚点功能在文档中垂直定位形状。通过设置形状的垂直锚点属性，您可以控制其相对于文本或页面的垂直对齐方式。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入并配置形状
使用`InsertShape`方法`DocumentBuilder`对象。设置形状所需的尺寸。

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## 步骤 4：设置垂直锚点
设置形状的垂直锚点属性以控制其垂直对齐方式。在此示例中，我们将其设置为“底部”，以将形状锚定在文本或页面的底部。

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## 步骤 5：向形状添加内容
使用`MoveTo`方法`DocumentBuilder`对象将光标移动到形状的第一个段落。然后，使用`Write`方法向形状添加内容。

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 步骤 6：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithShapes.VerticalAnchor.docx”。

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