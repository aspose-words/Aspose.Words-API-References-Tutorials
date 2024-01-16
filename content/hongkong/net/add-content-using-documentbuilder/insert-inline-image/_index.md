---
title: 在 Word 文件中插入內嵌影像
linktitle: 在 Word 文件中插入內嵌影像
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入內嵌映像。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/insert-inline-image/
---
在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 將內嵌圖像插入到 Word 文件中。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠將圖像直接新增至文件的文字中。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立新文件和 DocumentBuilder
首先，使用 Document 類別建立一個新文件並初始化 DocumentBuilder 物件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入內嵌影像
接下來，使用 DocumentBuilder 類別的 InsertImage 方法將內嵌影像插入文件中。提供影像檔案路徑作為參數：

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 第 3 步：儲存文檔
插入內嵌影像後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### 使用 Aspose.Words for .NET 插入內嵌映像的範例原始程式碼
以下是使用 Aspose.Words for .NET 插入內嵌影像的完整原始碼：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 將內嵌影像插入 Word 文件中。透過遵循逐步指南並利用提供的原始程式碼，現在您可以在文件文字中無縫添加圖像。

內嵌圖像適用於各種場景，例如將插圖、標誌或其他視覺元素直接新增至文件流程。

### 在Word文件中插入內嵌影像的常見問題解答

#### Q：我可以調整 Word 文件中內嵌影像的大小嗎？

答：是的，您可以使用 Aspose.Words for .NET 調整內嵌影像的大小。插入圖像後，您可以透過調整表示圖像的 Shape 物件的寬度和高度屬性來控制其大小。

#### Q：是否可以為內嵌影像添加替代文字以實現輔助功能？

答：是的，您可以為內嵌影像添加替代文字以增強可訪問性。 Aspose.Words for .NET 支援向圖像添加替代文本，允許螢幕閱讀器和其他輔助技術向視障用戶描述圖像內容。

#### Q：我可以對內嵌影像套用格式或樣式嗎？

答：當然！ Aspose.Words for .NET 為內嵌影像提供了廣泛的格式化選項。您可以對圖像套用各種樣式、邊框、效果和其他格式屬性，以符合文件的視覺設計。

#### Q：Aspose.Words for .NET 支援從串流或位元組陣列插入圖像嗎？

答：是的，您可以使用 Aspose.Words for .NET 從流或位元組陣列插入內嵌圖像。這允許您使用從外部來源載入的映像或動態生成的映像。

#### Q：我可以在文字內容的特定位置插入圖片嗎？

答：是的，Aspose.Words for .NET 中的 DocumentBuilder 類別提供了對內嵌影像插入位置的精確控制。您可以指定文字中應插入圖像的確切位置。