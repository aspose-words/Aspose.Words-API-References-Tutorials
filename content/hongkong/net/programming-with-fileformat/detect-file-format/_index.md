---
title: 檢測文件文件格式
linktitle: 檢測文件文件格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 偵測文件檔案格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-fileformat/detect-file-format/
---

本文提供了有關如何使用 Aspose.Words for .NET 的文件文件格式偵測功能的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何偵測不同文件檔案的格式。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 第 1 步：定義目錄

首先，您需要根據檔案的格式定義要儲存檔案的目錄。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。我們創建“Supported”、“Unknown”、“Encrypted”和“Pre97”目錄（如果它們尚未存在）。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

//如果目錄尚不存在，則建立它們。
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## 第 2 步：瀏覽文件

然後我們使用`GetFiles`的方法`Directory`類別取得指定目錄中的檔案清單。我們也使用一個`Where`子句排除名為“Corrupted document.docx”的特定檔案。

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 第三步：偵測每個文件的格式

我們循環遍歷列表中的每個文件並使用`DetectFileFormat`的方法`FileFormatUtil`類別來檢測文件的格式。我們也顯示偵測到的文件類型。

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

//顯示文檔類型
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
// ....新增其他支援的文件格式的案例
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

就這樣 ！您已使用 Aspose.Words for .NET 成功偵測到不同文件檔案的格式。

### 使用 Aspose.Words for .NET 進行檔案格式偵測的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	//如果目錄尚不存在，則建立它們。
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

		//顯示文檔類型
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

### 文件文件格式檢測常見問題解答

#### 如何使用 Aspose.Words for .NET 偵測文件檔案的格式？

若要使用 Aspose.Words for .NET 偵測文件檔案的格式，您可以按照教學課程中提供的步驟進行操作。使用`DetectFileFormat`的方法`FileFormatUtil`類別將允許您檢測文檔文件的格式。這將允許您確定它是 Microsoft Word 97-2003 文件、範本、Office Open XML WordprocessingML 文件還是其他支援的格式。本教程中提供的程式碼將引導您完成此功能的實作。

#### Aspose.Words for .NET 支援哪些文件格式？

Aspose.Words for .NET 支援多種文件格式，包含Microsoft Word 97-2003 文件(DOC)、範本(DOT)、Office Open XML WordprocessingML 文件(DOCX)、帶有巨集的Office Open XML WordprocessingML 文件(DOCM)、 Office Open不含巨集的XML WordprocessingML 範本(DOTX)、帶有巨集的Office Open XML WordprocessingML 範本(DOTM)、Flat OPC 文件、RTF 文件、Microsoft Word 2003 WordprocessingML 文件、HTML 文件、MHTML（Web 存檔）文件、OpenDocument (ODT) 文件、 OpenDocument 文字 (OTT) 範本、MS Word 6 或 Word 95 文件以及未知文件格式。

#### 格式偵測時如何處理加密文件檔案？

當偵測文檔文件的格式時，可以使用`IsEncrypted`的財產`FileFormatInfo`物件檢查文件是否已加密。如果檔案已加密，您可以採取其他步驟來處理這種特定情況，例如將檔案複製到專用於加密文件的目錄。您可以使用`File.Copy`方法來做到這一點。

#### 當文檔格式未知時應採取什麼措施？

當文件的格式未知時，您可以決定以特定於您的應用程式的方式處理它。在本教學提供的範例中，文件被複製到專用於未知格式文件的特定目錄中。您可以自訂此操作以滿足您的特定需求。

#### Aspose.Words for .NET 是否還有其他功能可以與文件格式偵測結合使用？

是的，Aspose.Words for .NET 提供了許多其他用於處理和操作 Word 文件的功能。例如，您可以使用該程式庫從文件中提取文字、圖像或元資料、套用格式變更、合併文件、將文件轉換為不同的格式等等。