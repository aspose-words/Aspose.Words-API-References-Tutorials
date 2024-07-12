---
title: 檢測帶有空格的編號
linktitle: 檢測帶有空格的編號
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中偵測帶有空格的清單編號。輕鬆改進文件的結構。
type: docs
weight: 10
url: /zh-hant/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
在本教程中，我們將探索為 Aspose.Words for .NET 的「偵測帶有空格的編號」功能提供的 C# 原始碼。此功能可讓您從包含清單編號後面接著空格的文字文件中偵測和建立清單。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：建立文字文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

在此步驟中，我們建立一個文字字串來模擬包含清單數字後面接著空格的文字文件。我們使用不同的清單分隔符，例如句點、右括號、項目符號和空格。

## 第 3 步：配置上傳選項

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

在此步驟中，我們配置文檔載入選項。我們創建一個新的`TxtLoadOptions`對象並設定`DetectNumberingWithWhitespaces`財產給`true`。這將允許 Aspose.Words 檢測清單編號，即使它們後面跟著空格。

## 第四步：載入文件並儲存

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

在此步驟中，我們使用指定的文字字串和載入選項來載入文件。我們使用一個`MemoryStream`將文字字串轉換為記憶體流。然後我們將產生的文件儲存為 .docx 格式。

### Aspose.Words for .NET 的空白編號偵測功能的範例原始碼。

```csharp

            
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
//建立一個字串形式的純文字文檔，其中的部分可以解釋為列表。
//載入後，前三個清單將始終被 Aspose.Words 偵測到，
//載入後將為它們建立 List 物件。
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

//第四個列表，列表編號和列表項目內容之間有空格，
//只有當 LoadOptions 物件中的「DetectNumberingWithWhitespaces」設為 true 時，才會將其偵測為列表，
//以避免以數字開頭的段落被錯誤地檢測為清單。
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

//將 LoadOptions 作為參數應用時載入文件並驗證結果。
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

現在，您可以執行原始程式碼來載入包含帶有空格的清單編號的文字文檔，然後使用偵測到的清單建立 .docx 文件。輸出檔案將保存在指定目錄中，名稱為「WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx」。

## 結論
在本教學中，我們探索了 Aspose.Words for .NET 中的空白編號偵測功能。我們學習如何從包含清單數字後面跟著空格的文字文件建立清單。

此功能對於處理包含以不同方式格式化的清單編號的文件非常有用。透過使用適當的載入選項，Aspose.Words 能夠偵測這些清單編號（即使它們後面跟著空格），並將它們轉換為最終文件中的結構化清單。

使用此功能可以節省您的時間並提高工作流程效率。您可以輕鬆地從文本文檔中提取信息，並將其轉換為具有適當列表的結構良好的文檔。

請記住考慮載入選項，例如配置空白撥號偵測，以達到所需的結果。

Aspose.Words for .NET 提供了許多用於文件操作和產生的高級功能。透過進一步探索 Aspose.Words 提供的文件和範例，您將能夠充分利用這個強大函式庫的功能。

因此，請毫不猶豫地將空白編號偵測整合到您的 Aspose.Words for .NET 專案中，並利用其優勢來建立結構良好且可讀的文件。


