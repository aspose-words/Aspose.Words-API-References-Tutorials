---
title: 将 Docx 转换为 Rtf
linktitle: 将 Docx 转换为 Rtf
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 Docx 转换为 RTF 格式。带有示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-rtf/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 RTF。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第1步：从Stream中读取文档

首先，打开一个流来读取Docx文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## 第 2 步：加载文档

接下来，从流加载文档：

```csharp
Document doc = new Document(stream);
```

## 第 3 步：关闭流

由于文档已加载到内存中，因此您可以关闭流：

```csharp
stream.Close();
```

## 第四步：对文档进行操作

此时，您可以对文档执行任何所需的操作。

## 第 5 步：将文档保存为 RTF 格式

要将文档保存为 RTF 格式，请将其保存到内存流：

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## 第 6 步：倒带流

在将内存流写入文件之前，将其位置回滚到零：

```csharp
dstStream.Position = 0;
```

## 第7步：将流写入文件

最后，将内存流写入RTF文件：

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

就是这样！您已使用 Aspose.Words for .NET 成功将 Docx 格式的 Word 文档转换为 RTF。

### 使用 Aspose.Words for .NET 的 Docx To Rtf 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//只读访问权限足以让 Aspose.Words 加载文档。
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//您现在可以关闭流，不再需要它，因为文档位于内存中。
	stream.Close();

	// ...对文档进行一些操作。

	//将文档转换为不同的格式并保存到流。
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	//将流位置倒回到零，以便为下一个读取器做好准备。
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

请随意在您自己的项目中使用此代码，并根据您的具体要求进行修改。

### 常见问题解答

#### 如何将 DOCX 文件转换为 RTF 格式？

要将 DOCX 文件转换为 RTF 格式，您可以使用提供此功能的各种软件工具或库。 Aspose.Words for .NET 就是这样一种可靠的工具。它提供了一种简单有效的方法，以编程方式将 DOCX 文件转换为 RTF 格式。您可以使用该库的 API 加载 DOCX 文件并将其保存为所需的 RTF 格式。

#### 转换过程是否有任何限制？

转换过程的限制取决于您使用的特定工具或库。某些工具可能对输入文档的大小或复杂性有限制。选择能够满足转换任务要求的工具非常重要。

#### 我可以保留原始文档的格式和布局吗？

是的，使用 Aspose.Words，您可以在转换过程中保留原始文档的格式和布局。例如，Aspose.Words for .NET 为在转换后的 RTF 文档中维护 DOCX 文件的格式、样式和其他元素提供了全面的支持。

#### Aspose 是 DOCX 到 RTF 转换的可靠工具吗？

是的，Aspose.Words for .NET 是一款高度可靠的 DOCX 到 RTF 转换工具。它以其强大的功能和卓越的性能而被全球开发人员和企业广泛使用。该库提供广泛的文档、定期更新和专门的技术支持，使其成为文档转换任务的值得信赖的选择。