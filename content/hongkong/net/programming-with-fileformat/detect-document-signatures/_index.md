---
title: 檢測 Word 文件上的數位簽名
linktitle: 檢測 Word 文件上的數位簽名
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 偵測 Word 文件上的數位簽章的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-fileformat/detect-document-signatures/
---

本文提供了有關如何透過 Aspose.Words for .NET 使用 Word 文件偵測功能的數位簽章的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何偵測文件中的數位簽章。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：偵測數位簽名

接下來，我們使用`DetectFileFormat`的方法`FileFormatUtil`類別來檢測文件格式資訊。在此範例中，我們假設文件名稱為「Digitallysigned.docx」並且位於指定的文件目錄中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## 第 3 步：檢查數位簽名

我們使用以下方法檢查文件是否包含數位簽名`HasDigitalSignature`的財產`FileFormatInfo`目的。如果偵測到數位簽名，我們會顯示一則訊息，指示如果使用 Aspose.Words 開啟/儲存文檔，簽名將會遺失。

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

就這樣 ！您已使用 Aspose.Words for .NET 成功偵測到文件中的數位簽章。

### 使用 Aspose.Words for .NET 偵測文件簽章的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
## 結論

本教學為您提供如何使用 Aspose.Words for .NET 的數位簽章偵測功能來偵測 Word 文件上的數位簽章的逐步指南。程式碼的每個部分都進行了詳細解釋，讓您了解如何檢測文件中的數位簽章。

### 檢測 Word 文件數位簽章的常見問題解答

#### 如何使用 Aspose.Words for .NET 偵測 Word 文件中是否有數位簽章？

若要使用 Aspose.Words for .NET 偵測 Word 文件上是否有數位簽名，您可以按照教學課程中提供的步驟進行操作。使用`DetectFileFormat`的方法`FileFormatUtil`類別將允許您檢測文件格式資訊。然後你可以檢查`HasDigitalSignature`的財產`FileFormatInfo`物件確定文件是否包含數位簽章。如果偵測到數位簽名，您可以顯示一則訊息，指出如果使用 Aspose.Words 開啟/儲存文檔，簽名將會遺失。

#### 如何指定包含要在其中搜尋數位簽章的文件的目錄？

若要指定包含要搜尋數位簽章的文件的目錄，必須修改`dataDir`程式碼中的變數。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

#### 使用 Aspose.Words 開啟/儲存文件對數位簽章有何影響？

當您使用 Aspose.Words 開啟或儲存文件時，文件中存在的數位簽章將會遺失。這是由於在使用 Aspose.Words 處理時對文件進行了更改。如果您需要保留數位簽名，則應考慮到這一點並使用其他方法來管理包含數位簽名的文件。

#### Aspose.Words for .NET 的哪些其他功能可以與數位簽章偵測結合使用？

 Aspose.Words for .NET 提供了多種用於處理和操作 Word 文件的功能。除了檢測數位簽章之外，您還可以使用該庫從文件中提取文字、圖像或元資料、應用程式格式變更、合併文件、將文件轉換為不同的格式等等。您可以探索[Aspose.Words for .NET API 參考](https://reference.aspose.com/words/net/)發現所有可用的功能並找到最適合您需求的功能。

#### 使用 Aspose.Words for .NET 偵測數位簽章有哪些限制？

Aspose.Words for .NET 的數位簽章偵測僅限於偵測文件中是否有簽章。但是，Aspose.Words 不提供驗證數位簽章的真實性或完整性的功能。若要對數位簽章執行更進階的操作，您將需要使用其他專用工具或函式庫。