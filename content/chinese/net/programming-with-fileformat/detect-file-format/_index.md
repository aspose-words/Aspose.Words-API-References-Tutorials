---
title: 检测文档文件格式
linktitle: 检测文档文件格式
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 检测文档文件格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-fileformat/detect-file-format/
---

本文提供了有关如何使用 Aspose.Words for .NET 的文档文件格式检测功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何检测不同文档文件的格式。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤 1：定义目录

首先，您需要根据文件的格式定义要存储文件的目录。替换`"YOUR DOCUMENT DIRECTORY"`替换为文档目录的实际路径。如果“Supported”、“Unknown”、“Encrypted”和“Pre97”目录尚不存在，我们将创建这些目录。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

//如果目录不存在，请创建目录。
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## 第 2 步：浏览文件

然后我们使用`GetFiles`方法`Directory`类来获取指定目录中的文件列表。我们还使用`Where`子句来排除名为“Corrupted document.docx”的特定文件。

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 步骤 3：检测每个文件的格式

我们循环遍历列表中的每个文件并使用`DetectFileFormat`方法`FileFormatUtil`类来检测文件的格式。我们还显示检测到的文档类型。

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

//显示文档类型
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... 添加其他支持的文档格式的案例
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

就这样！您已成功使用 Aspose.Words for .NET 检测不同文档文件的格式。

### 使用 Aspose.Words for .NET 进行文件格式检测的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	//如果目录不存在，则创建目录。
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		//显示文档类型
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### 文档文件格式检测常见问题解答

#### 如何使用 Aspose.Words for .NET 检测文档文件的格式？

要使用 Aspose.Words for .NET 检测文档文件的格式，您可以按照教程中提供的步骤进行操作。使用`DetectFileFormat`方法`FileFormatUtil`类将允许您检测文档文件的格式。这将允许您确定它是 Microsoft Word 97-2003 文档、模板、Office Open XML WordprocessingML 文档还是其他受支持的格式。本教程中提供的代码将引导您实现此功能。

#### Aspose.Words for .NET 支持哪些文档格式？

Aspose.Words for .NET 支持多种文档格式，包括 Microsoft Word 97-2003 文档 (DOC)、模板 (DOT)、Office Open XML WordprocessingML 文档 (DOCX)、带有宏的 Office Open XML WordprocessingML 文档 (DOCM)、不带宏的 Office Open XML WordprocessingML 模板 (DOTX)、带有宏的 Office Open XML WordprocessingML 模板 (DOTM)、平面 OPC 文档、RTF 文档、Microsoft Word 2003 WordprocessingML 文档、HTML 文档、MHTML (Web 存档) 文档、OpenDocument 文本 (ODT) 文档、OpenDocument 文本 (OTT) 模板、MS Word 6 或 Word 95 文档以及未知文档格式。

#### 格式检测时如何处理加密文档文件？

检测文档文件的格式时，可以使用`IsEncrypted`的财产`FileFormatInfo`对象来检查文件是否已加密。如果文件已加密，您可以采取其他步骤来处理这种特定情况，例如将文件复制到专用于加密文档的目录中。您可以使用`File.Copy`方法来做到这一点。

#### 当文档格式未知时应该采取什么措施？

当文档格式未知时，您可以决定以特定于应用程序的方式处理它。在本教程提供的示例中，文档被复制到专用于未知格式文档的特定目录中。您可以自定义此操作以满足您的特定需求。

#### Aspose.Words for .NET 还有其他功能可以与文档格式检测结合使用吗？

是的，Aspose.Words for .NET 提供了许多其他用于处理和操作 Word 文档的功能。例如，您可以使用该库从文档中提取文本、图像或元数据、应用格式更改、合并文档、将文档转换为不同格式等等。