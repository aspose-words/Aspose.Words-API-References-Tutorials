---
title: 刪除 PDF 檔案中的註釋
linktitle: 刪除 PDF 檔案中的註釋
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 刪除 PDF 檔案中的註解。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/remove-comments-in-pdf/
---

在本逐步指南中，我們將告訴您如何使用 Aspose.Words for .NET 刪除 PDF 檔案中的註解。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是載入包含註解的文檔。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：隱藏 PDF 中的註釋

我們將配置佈局選項以在產生 PDF 時隱藏註釋。

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 步驟 3：將文件另存為 PDF

最後，我們透過刪除註解將文件儲存為PDF格式。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown 輸出格式

輸出可以採用 Markdown 格式以提高可讀性。例如 ：

```markdown
- Comments are hidden in the generated PDF.
```

### 使用 Aspose.Words for .NET 刪除 Pdf 中的註解的範例原始程式碼

以下是使用 Aspose.Words for .NET 刪除 PDF 檔案中註解的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

//隱藏 PDF 中的註釋。
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 從 PDF 檔案中刪除註解。透過使用適當的佈局選項，我們能夠在生成 PDF 時隱藏註釋。 Aspose.Words for .NET 提供了極大的靈活性來操作 Word 文件並將其轉換為不同的格式，包括 PDF。現在您可以應用這些知識，使用 Aspose.Words for .NET 刪除您自己的 PDF 檔案中的註解。

### 刪除 pdf 檔案中註釋的常見問題解答

#### Q：如何在 Aspose.Words for .NET 中上傳文件？

答：使用`Document`用於從文件載入文件的 Aspose.Words for .NET 類別。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何隱藏使用 Aspose.Words for .NET 產生的 PDF 中的註解？

答：使用`CommentDisplayMode`的財產`LayoutOptions`物件來配置產生 PDF 時註解的顯示方式。若要隱藏評論，請將此屬性設為`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q：如何使用 Aspose.Words for .NET 將文件儲存為 PDF？

答：使用`Save`的方法`Document`物件以 PDF 格式儲存文件。指定 PDF 檔案的完整路徑。

```csharp
doc.Save("path/to/the/file.pdf");
```