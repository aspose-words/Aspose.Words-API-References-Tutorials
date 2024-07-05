---
title: 验证加密的 Word 文档
linktitle: 验证加密的 Word 文档
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 加密的分步指南来验证 Word 文档是否加密。
type: docs
weight: 10
url: /zh/net/programming-with-fileformat/verify-encrypted-document/
---

本文提供了有关如何使用 Aspose.Words for .NET 的加密 Word 文档验证功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何检查文档是否已加密。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤1：定义文档目录

首先，您需要定义文档所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：检测文件格式

接下来，我们使用`DetectFileFormat`方法`FileFormatUtil`类来检测文件格式信息。在此示例中，我们假设加密文档名为“Encrypted.docx”，位于指定的文档目录中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 步骤 3：检查文档是否加密

我们使用`IsEncrypted`的财产`FileFormatInfo`对象来检查文档是否已加密。此属性返回`true`如果文档已加密，否则返回`false`.我们在控制台中显示结果。

```csharp
Console.WriteLine(info.IsEncrypted);
```

就这样！您已成功检查文档是否使用 Aspose.Words for .NET 加密。

### 使用 Aspose.Words for .NET 验证加密文档的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## 经常问的问题

### 问：验证加密的 Word 文档的步骤是什么？

验证加密的Word文档的步骤如下：

定义文档目录。

检测文件格式。

检查文档是否已加密。

### 问：如何设置文档目录？
要设置文档目录，您需要替换`"YOUR DOCUMENT DIRECTORY"`使用以下代码中的文档目录的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### 问：如何检测文件格式？
您可以使用`DetectFileFormat`方法`FileFormatUtil`类来检测文件格式信息。在下面的例子中，我们假设加密文档名为“Encrypted.docx”，位于指定的文档目录中：

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### 问：如何检查文档是否加密？
您可以使用`IsEncrypted`的财产`FileFormatInfo`对象来检查文档是否已加密。此属性返回`true`如果文档已加密，否则返回`false`.结果显示在控制台中：

```csharp
Console.WriteLine(info.IsEncrypted);
```

### 问：如何使用 Aspose.Words for .NET 检查文档是否加密？
通过按照本教程中提到的步骤并运行提供的源代码，您可以检查文档是否使用 Aspose.Words for .NET 加密。
