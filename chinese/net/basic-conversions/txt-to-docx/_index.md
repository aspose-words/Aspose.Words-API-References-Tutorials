---
title: 文本转文档
linktitle: 文本转文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将纯文本文件 (Txt) 转换为 Word 文档 (Docx)。带有示例代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/txt-to-docx/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将纯文本文件 (Txt) 转换为 Docx 格式的 Word 文档。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供纯文本文件的路径来对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## 第 2 步：将文档保存为 Docx 格式

接下来，通过调用将文档保存为 Docx 格式`Save`上的方法`Document`对象并提供输出 Docx 文档的路径和文件名：

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将纯文本文件 (Txt) 转换为 Docx 格式的 Word 文档。

### 使用 Aspose.Words for .NET 的 Txt To Docx 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//自动检测文本文件的编码。
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。