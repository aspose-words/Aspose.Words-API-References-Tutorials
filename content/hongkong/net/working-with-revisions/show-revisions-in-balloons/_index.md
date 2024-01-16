---
title: 在氣球中顯示修訂
linktitle: 在氣球中顯示修訂
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 在氣球中顯示修訂。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/show-revisions-in-balloons/
---

在本逐步指南中，我們將向您展示如何使用 Aspose.Words for .NET 在 Word 文件中的氣球中顯示修訂。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是上傳包含修訂的文檔。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：設定評論顯示選項

我們將配置顯示選項以使修訂在氣球中可見。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 步驟 3：將文件儲存為 PDF 格式

最後，我們將文件儲存為 PDF，修訂內容顯示在氣球中。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown 輸出格式

輸出可以採用 Markdown 格式以提高可讀性。例如 ：

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### 使用 Aspose.Words for .NET 在氣球中顯示已修訂的範例原始程式碼

以下是使用 Aspose.Words for .NET 在文件中的氣球中顯示修訂的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

//渲染內聯插入修訂、刪除氣球中的修訂以及格式化修訂。
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
//在頁面右側呈現修訂欄。
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件中的氣球中顯示修訂。透過使用適當的顯示選項，我們能夠在氣泡中顯示修訂，並在右側顯示修訂欄。 Aspose.Words for .NET 提供了許多強大的功能來操作 Word 文檔，包括修訂管理。現在，您可以利用這些知識，使用 Aspose.Words for .NET 在您自己的 Word 文件中的氣球中顯示修訂。


### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中上傳文件？

答：使用`Document`用於從文件載入文件的 Aspose.Words for .NET 類別。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何使用 Aspose.Words for .NET 在氣球中顯示修訂版本？

答：使用`ShowInBalloons`的財產`RevisionOptions`物件來配置氣球中修訂的顯示。您可以將此屬性設為`ShowInBalloons.FormatAndDelete`在氣球中顯示帶有刪除和格式修訂的修訂。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q：如何使用 Aspose.Words for .NET 將文件儲存為 PDF 格式？

答：使用`Save`的方法`Document`物件以 PDF 格式儲存文件。您必須指定具有“.pdf”副檔名的完整目標路徑。

```csharp
doc.Save("path/to/destination/document.pdf");
```