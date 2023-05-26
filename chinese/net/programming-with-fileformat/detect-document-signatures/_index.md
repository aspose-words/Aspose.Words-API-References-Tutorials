---
title: 检测文档签名
linktitle: 检测文档签名
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 检测文档中数字签名的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-fileformat/detect-document-signatures/
---

本文提供了有关如何使用 Aspose.Words for .NET 的文档签名检测功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何检测文档中的数字签名。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：检测数字签名

接下来，我们使用`DetectFileFormat`的方法`FileFormatUtil`检测文件格式信息的类。在此示例中，我们假设文档名为“Digitally signed.docx”并且位于指定的文档目录中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## 第 3 步：检查数字签名

我们检查文档是否包含数字签名使用`HasDigitalSignature`的财产`FileFormatInfo`目的。如果检测到数字签名，我们会显示一条消息，表明如果使用 Aspose.Words 打开/保存文档，签名将会丢失。

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

就这样 ！您已经使用 Aspose.Words for .NET 成功检测到文档中的数字签名。

### 使用 Aspose.Words for .NET 检测文档签名的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
