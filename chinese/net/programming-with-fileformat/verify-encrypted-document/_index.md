---
title: 验证加密文件
linktitle: 验证加密文件
second_title: Aspose.Words for .NET API 参考
description: 验证文档是否使用 Aspose.Words for .NET 加密的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-fileformat/verify-encrypted-document/
---

本文提供了有关如何使用 Aspose.Words for .NET 的加密文档验证功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何检查文档是否已加密。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：检测文件格式

接下来，我们使用`DetectFileFormat`的方法`FileFormatUtil`检测文件格式信息的类。在此示例中，我们假设加密文档名为“Encrypted.docx”，位于指定的文档目录中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 第 3 步：检查文档是否已加密

我们使用`IsEncrypted`的财产`FileFormatInfo`对象以检查文档是否已加密。该属性返回`true`如果文档被加密，否则返回`false`.我们在控制台中显示结果。

```csharp
Console.WriteLine(info.IsEncrypted);
```

就这样 ！您已成功检查文档是否使用 Aspose.Words for .NET 加密。

### 使用 Aspose.Words for .NET 验证加密文档的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```
