---
title: Docx 转字节
linktitle: Docx 转字节
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 Docx 转换为字节数组。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-byte/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为字节数组。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化 MemoryStream

首先，创建一个实例`MemoryStream`将转换后的文档存储为字节数组的类：

```csharp
MemoryStream outStream = new MemoryStream();
```

## 第 2 步：将文档保存到 MemoryStream

接下来，使用`Save`的方法`Document`类将文档保存到`MemoryStream`Docx 格式：

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## 第 3 步：将 MemoryStream 转换为字节数组

转换`MemoryStream`将 Docx 文档包含到字节数组中，使用`ToArray`方法：

```csharp
byte[] docBytes = outStream.ToArray();
```

## 第 4 步：从字节数组初始化 MemoryStream

现在，初始化一个新的实例`MemoryStream`使用在上一步中获得的字节数组：

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## 第 5 步：从 MemoryStream 创建文档

最后，创建一个新的`Document`对象来自`MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 Docx 格式的 Word 文档转换为字节数组。

### 使用 Aspose.Words for .NET 的 Docx To Byte 示例源代码

```csharp

	//MemoryStream outStream = new MemoryStream();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。