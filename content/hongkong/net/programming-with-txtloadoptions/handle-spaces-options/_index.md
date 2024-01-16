---
title: 處理空間選項
linktitle: 處理空間選項
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 管理 TXT 文件中的空格。刪除不必要的空格並提高可讀性。
type: docs
weight: 10
url: /zh-hant/net/programming-with-txtloadoptions/handle-spaces-options/
---

在本教學中，我們將探索為 Aspose.Words for .NET 的「使用 TXT 載入選項管理空間」功能提供的 C# 原始碼。此功能可讓您在載入 TXT 文件時指定空白處理行為。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：建立文字文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

在此步驟中，我們建立一個文字字串，用於模擬包含帶有前導空格和尾隨空格的行的文字文件。

## 第 3 步：配置上傳選項

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

在此步驟中，我們配置載入 TXT 文件的選項。我們創建一個新的`TxtLoadOptions`對象並設定`LeadingSpacesOptions`和`TrailingSpacesOptions`屬性到`TxtLeadingSpacesOptions.Trim`和`TxtTrailingSpacesOptions.Trim`分別。這告訴 Aspose.Words 在載入文件時刪除行中的前導和尾隨空格。

## 第 4 步：載入文檔

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並傳遞包含指定文字字串和載入選項的記憶體流。

## 第 5 步：儲存文檔

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

在最後一步中，我們使用以下命令將產生的文件儲存為 .docx 格式：`Save`方法並傳遞輸出檔案的路徑。

現在，您可以運行原始程式碼透過指定空白處理選項來載入文字文件。產生的文件將保存在指定目錄中，名稱為「WorkingWithTxtLoadOptions.HandleSpacesOptions.docx」。

### 帶有 TXT 載入選項的空間管理功能範例原始程式碼以及 Aspose.Words for .NET*

```csharp

            
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## 結論

在本教學中，我們探索了在 Aspose.Words for .NET 中使用 TXT 載入選項管理空間的功能。我們學習如何在載入 TXT 文件時指定空白處理行為。

此功能對於處理文件中行左右兩側不必要的空格非常有用。透過配置適當的載入選項，您可以輕鬆刪除這些不需要的空格，這有助於使文件內容更清晰、更具可讀性。

Aspose.Words for .NET 提供了許多用於文件操作和產生的高級功能。載入 TXT 文件時管理空間是它為您提供的眾多強大工具之一。

選擇最適合您的特定場景的空間管理選項非常重要。在這個例子中，我們使用了`Trim`用於刪除行首和行尾不必要空格的選項。但是，Aspose.Words 還具有其他選項來保留空格、完全刪除空格或保持原樣。

不要忘記根據您的特定需求和 TXT 文件的結構調整這些選項。

使用 Aspose.Words for .NET，您可以輕鬆操作文件中的空白，從而提高佈局品質和內容可讀性。

因此，請毫不猶豫地將空白管理與 Aspose.Words for .NET 專案中的 TXT 載入選項集成，並利用其優勢來創建格式良好且易於閱讀的文件。