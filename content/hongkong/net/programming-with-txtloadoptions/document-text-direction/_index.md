---
title: 文檔文字方向
linktitle: 文檔文字方向
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在文件中指定文字方向。改進從右到左語言的顯示。
type: docs
weight: 10
url: /zh-hant/net/programming-with-txtloadoptions/document-text-direction/
---

在本教程中，我們將探索為 Aspose.Words for .NET 的「文件文字方向」功能提供的 C# 原始程式碼。此功能可讓您指定文件中文字的方向，這對於從右向左書寫的語言（例如希伯來語或阿拉伯語）特別有用。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：配置上傳選項

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

在此步驟中，我們配置文檔載入選項。我們創建一個新的`TxtLoadOptions`對象並設定`DocumentDirection`財產給`DocumentDirection.Auto`。該值告訴 Aspose.Words 根據文件內容自動確定文字方向。

## 第 3 步：載入文檔

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並傳遞要載入的文字檔案的路徑。我們也使用指定的載入選項。

## 步驟 4：操作段落並顯示文字方向

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

在此步驟中，我們使用以下命令存取文件的第一段`FirstSection`和`Body`特性。接下來，我們訪問`ParagraphFormat.Bidi`屬性來取得段落的文字方向。然後我們在控制台中顯示該值。

## 第 5 步：儲存文檔

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

在最後一步中，我們使用以下命令將產生的文件儲存為 .docx 格式：`Save`方法並傳遞輸出檔案的路徑。

現在您可以運行原始程式碼來載入文字文件並確定文字方向。產生的文件將保存在指定目錄中，名稱為「WorkingWithTxtLoadOptions.DocumentTextDirection.docx」。

### 使用 Aspose.Words for .NET 實作文件文字方向功能的範例原始碼。


```csharp

            
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## 結論

在本教學中，我們探索了 Aspose.Words for .NET 中的文件文字方向功能。我們學習如何指定文件中文字的方向，特別是對於從右到左書寫的語言，例如希伯來語或阿拉伯語。

此功能對於確保文字在多語言文件中正確顯示至關重要。透過使用適當的載入選項，Aspose.Words 可以自動偵測文字的方向並將其套用到文件。

使用Aspose.Words，您可以輕鬆操縱文件中文字的方向，為使用者提供流暢直觀的閱讀體驗。

值得注意的是，當使用需要特定文字方向的語言進行文字處理時，此功能特別有用。 Aspose.Words 透過提供強大的工具來管理文件中文字的方向，使這項任務變得容易。

請記住使用適當的載入選項（例如設定自動文字方向）以獲得您想要的文件結果。

Aspose.Words for .NET 提供了許多用於文件操作和產生的高級功能。透過進一步探索 Aspose.Words 提供的文件和範例，您將能夠充分利用這個強大函式庫的功能。

因此，請毫不猶豫地將文件文字方向整合到您的 Aspose.Words for .NET 專案中，並利用其優勢來創建有吸引力的高品質多語言文件。