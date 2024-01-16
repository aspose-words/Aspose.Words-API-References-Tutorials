---
title: 載入語言的連字詞典
linktitle: 載入語言的連字詞典
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中載入特定語言的連字字典。
type: docs
weight: 10
url: /zh-hant/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

在本逐步教學中，我們將向您展示如何將特定語言的連字符字典載入到 Aspose.Words for .NET 中。我們將解釋提供的 C# 原始程式碼並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有安裝該庫，請從以下位置下載並安裝該庫：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：載入文檔

首先，從指定目錄載入文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 第 2 步：載入連字符字典

接下來，打開連字符字典檔案的流並將其儲存為所需的語言。在此範例中，我們載入瑞士德語 (de-CH) 字典：

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

確保資料目錄中有適當的字典檔案。

## 第三步：儲存修改後的文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

所以 ！您已成功在 Aspose.Words for .NET 中載入特定語言的連字字典。

### 使用 Aspose.Words for .NET 載入連字符字典的範例原始程式碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

請隨意在您自己的專案中使用此程式碼並對其進行修改以滿足您的特定需求。

### 常見問題解答

#### Q：如何在 Aspose.Words 中載入特定語言的音節字典？

答：要在 Aspose.Words 中載入特定語言的音節字典，您可以使用`Hyphenation`類和`LoadDictionary()`方法。建立一個實例`Hyphenation`類別並調用`LoadDictionary()`方法指定所需語言的音節字典檔案的路徑。這會將音節字典載入到 Aspose.Words 中。

#### Q：在哪裡可以找到不同語言的音節字典檔案？

答：您可以在各種線上資源上找到不同語言的音節字典檔案。這些檔案通常是 XML 或 TEX 格式。您可以在專門用於語言學專案或原始碼儲存庫的網站上找到不同語言的開源音節詞典。

#### Q：如何將載入的音節字典套用到 Aspose.Words 中的文件？

答：要將載入的音節字典套用到 Aspose.Words 中的文檔，您需要迭代文檔中的單字並使用`Hyphenate()`的方法`Hyphenation`類別來取得單字的音節。然後，您可以根據需要設定音節單字的格式，例如在音節之間新增連字符。

#### Q：Aspose.Words 支援哪些語言進行音節化？

答：Aspose.Words 支援多種語言的音節化，包括英語、法語、西班牙語、德語、義大利語、荷蘭語、俄語、葡萄牙語、瑞典語、挪威語、丹麥語、芬蘭語、波蘭語、捷克語等。檢查 Aspose.Words 文件以取得支援音節化的語言的完整清單。