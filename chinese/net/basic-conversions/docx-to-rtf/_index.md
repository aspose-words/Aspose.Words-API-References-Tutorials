---
title: Docx 转 Rtf
linktitle: Docx 转 Rtf
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 Docx 格式转换为 RTF 格式。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-rtf/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 RTF。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：从流中读取文档

首先，打开一个流来读取 Docx 文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## 第 2 步：装入文档

接下来，从流中加载文档：

```csharp
Document doc = new Document(stream);
```

## 第 3 步：关闭流

由于文档已加载到内存中，您可以关闭流：

```csharp
stream.Close();
```

## 第四步：对文档进行操作

此时，您可以对文档执行任何需要的操作。

## 第 5 步：将文档保存为 RTF 格式

要以 RTF 格式保存文档，请将其保存到内存流中：

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## 第 6 步：倒带流

在将内存流写入文件之前，将其位置倒回到零：

```csharp
dstStream.Position = 0;
```

## 第 7 步：将流写入文件

最后，将内存流写入RTF文件：

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 Docx 格式的 Word 文档转换为 RTF。

### 使用 Aspose.Words for .NET 的 Docx To Rtf 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//只读权限足以让 Aspose.Words 加载文档。
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//您现在可以关闭流，不再需要它，因为文档在内存中。
	stream.Close();

	// ...对文件做些什么。

	//将文档转换为不同的格式并保存到流中。
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	//将流位置倒回到零，以便为下一个读者做好准备。
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。