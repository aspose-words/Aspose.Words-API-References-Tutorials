---
title: 設定字體強調標記
linktitle: 設定字體強調標記
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定字體強調樣式。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-font-emphasis-mark/
---

在本教學中，我們將向您展示如何使用 Aspose.Words for .NET 在 Word 文件中設定字體強調樣式。字體強調用於突出顯示文字中的某些單字或短語。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫

## 步驟1：定義文檔目錄
首先將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立並自訂文檔
建立一個實例`Document`類別和關聯的`DocumentBuilder`建構文檔內容。使用`Font.EmphasisMark`屬性將字體強調樣式設定為`EmphasisMark.UnderSolidCircle`。然後使用`Write`和`Writeln`的方法`DocumentBuilder`新增具有指定字體強調的文字。

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 步驟 3：儲存文檔
使用儲存文檔`Save`的方法`Document`具有適當的路徑和檔案名稱。

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### 使用 Aspose.Words for .NET 設定字體強調標記的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## 結論
在本教學中，您學習如何使用 Aspose.Words for .NET 在 Word 文件中設定字體強調樣式。嘗試不同的強調風格，並使用此功能突出顯示文件中的單字或短語。

### 常見問題解答

#### Q：如何使用 Aspose.Words 將重音符號新增至 Word 文件中的特定字體？

答：要使用 Aspose.Words 將重音標記新增至 Word 文件中的特定字體，您可以使用 API 導覽至所需的字體並套用適當的重音標記。這將為具有所選字體的文字添加重音符號。

#### Q：是否可以使用 Aspose.Words 來變更 Word 文件中重音符號的樣式？

答：是的，使用 Aspose.Words，您可以變更 Word 文件中重音符號的樣式。此 API 可讓您調整顏色、大小、線型等樣式屬性，以自訂重音標記的外觀。

#### Q：如何使用 Aspose.Words 刪除 Word 文件中的所有重音符號？

答：要使用 Aspose.Words 從 Word 文件中刪除所有重音符號，您可以使用 API 瀏覽文件、偵測現有重音符號並使用適當的方法將其刪除。這將從文件中刪除所有強調標記。

#### Q：我可以在 Word 文件中的文字的特定部分中添加重音符號嗎？

答：是的，您可以使用 Aspose.Words 將重音符號新增至 Word 文件中文字的特定部分。您可以使用 API 選擇所需的文字範圍，並在該文字部分中添加適當的強調標記。

#### Q：重音符號可以依照我的需求客製嗎？

答：是的，可以使用 Aspose.Words 根據您的需求自訂重音符號。您可以調整重音標記的樣式屬性，例如顏色、大小、線型等，以符合您的格式首選項。