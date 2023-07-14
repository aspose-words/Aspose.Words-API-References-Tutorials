---
title: 检测 Word 文档上的数字签名
linktitle: 检测 Word 文档上的数字签名
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 检测 Word 文档上的数字签名的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-fileformat/detect-document-signatures/
---

本文提供了有关如何通过 Aspose.Words for .NET 使用 Word 文档检测功能的数字签名的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何检测文档中的数字签名。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：检测数字签名

接下来，我们使用`DetectFileFormat`的方法`FileFormatUtil`类来检测文件格式信息。在此示例中，我们假设文档名为“Digitallysigned.docx”并且位于指定的文档目录中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## 第 3 步：检查数字签名

我们使用以下方法检查文档是否包含数字签名`HasDigitalSignature`的财产`FileFormatInfo`目的。如果检测到数字签名，我们会显示一条消息，指示如果使用 Aspose.Words 打开/保存文档，签名将会丢失。

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

就这样 ！您已使用 Aspose.Words for .NET 成功检测到文档中的数字签名。

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
## 结论

本教程为您提供了如何使用 Aspose.Words for .NET 的数字签名检测功能来检测 Word 文档上的数字签名的分步指南。代码的每个部分都进行了详细解释，让您了解如何检测文档中的数字签名。

### 检测 Word 文档数字签名的常见问题解答

#### 如何使用 Aspose.Words for .NET 检测 Word 文档中是否存在数字签名？

要使用 Aspose.Words for .NET 检测 Word 文档上是否存在数字签名，您可以按照教程中提供的步骤进行操作。使用`DetectFileFormat`的方法`FileFormatUtil`类将允许您检测文件格式信息。然后你可以检查`HasDigitalSignature`的财产`FileFormatInfo`对象确定文档是否包含数字签名。如果检测到数字签名，您可以显示一条消息，指出如果使用 Aspose.Words 打开/保存文档，签名将会丢失。

#### 如何指定包含要在其中搜索数字签名的文档的目录？

要指定包含要在其中搜索数字签名的文档的目录，必须修改`dataDir`代码中的变量。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

#### 使用 Aspose.Words 打开/保存文档对数字签名有何影响？

当您使用 Aspose.Words 打开或保存文档时，文档中存在的数字签名将会丢失。这是由于在使用 Aspose.Words 处理时对文档进行了更改。如果您需要保留数字签名，则应考虑到这一点并使用其他方法来管理包含数字签名的文档。

#### Aspose.Words for .NET 的哪些其他功能可以与数字签名检测结合使用？

Aspose.Words for .NET 提供了多种用于处理和操作 Word 文档的功能。除了检测数字签名之外，您还可以使用该库从文档中提取文本、图像或元数据、应用格式更改、合并文档、将文档转换为不同的格式等等。您可以浏览 Aspose.Words for .NET 的官方文档，以发现所有可用的功能并找到最适合您需求的功能。

#### 使用 Aspose.Words for .NET 检测数字签名有哪些限制？

Aspose.Words for .NET 的数字签名检测仅限于检测文档中是否存在签名。但是，Aspose.Words 不提供验证数字签名的真实性或完整性的功能。要对数字签名执行更高级的操作，您将需要使用其他专用工具或库。