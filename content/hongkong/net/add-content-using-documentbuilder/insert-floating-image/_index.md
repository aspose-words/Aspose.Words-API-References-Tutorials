---
title: 在Word文件中插入浮動影像
linktitle: 在Word文件中插入浮動影像
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入浮動圖像。逐步指南。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/insert-floating-image/
---
在這個綜合範例中，您將學習如何使用 Aspose.Words for .NET 將浮動圖像插入到 Word 文件中。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠在文件中新增具有可自訂定位和換行選項的影像。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立新文件和 DocumentBuilder
首先，使用 Document 類別建立一個新文件並初始化 DocumentBuilder 物件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入浮動影像
接下來，使用 DocumentBuilder 類別的 InsertImage 方法插入浮動影像。提供影像檔案路徑、相對水平和垂直位置、寬度、高度和換行選項作為參數：

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## 第 3 步：儲存文檔
插入浮動影像後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## 使用 Aspose.Words for .NET 插入浮動圖像的範例原始程式碼
以下是使用 Aspose.Words for .NET 插入浮動影像的完整原始碼：
浮動圖像適用於各種場景，例如添加可以獨立於文件文字放置的標誌、插圖或裝飾元素。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

請記住根據您的特定要求調整程式碼，包括影像檔案路徑以及所需的定位和換行選項。

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 將浮動圖像插入到 Word 文件中。透過遵循逐步指南並利用提供的原始程式碼，您現在可以使用具有視覺吸引力和可自訂的浮動影像來增強文件。

### 在word文件中插入浮動影像的常見問題

#### Q：我可以在一個文件中插入多個浮動影像嗎？

答：當然可以！您可以使用 Aspose.Words for .NET 在 Word 文件中插入任意數量的浮動圖像。只需重複插入過程即可添加多個視覺上吸引人的圖像。

#### Q：浮動影像有哪些環繞選項可用？

答：Aspose.Words for .NET 為浮動影像提供了多種環繞選項，包括 Square、Tight、Through、TopBottom 和 None。這些選項決定文字如何與浮動圖像互動。

#### Q：我可以調整浮動影像的大小嗎？

答：當然！您可以使用 InsertImage 方法中的對應參數來指定浮動影像的寬度和高度。這使您可以根據您的設計偏好控制圖像的尺寸。

#### Q：我可以相對於文件中的特定元素定位浮動影像嗎？

答：是的，Aspose.Words for .NET 可讓您相對於特定元素定位浮動影像，例如邊距、頁面、段落或表格。您可以選擇適當的相對水平和垂直位置參數來實現所需的放置。

#### Q：Aspose.Words for .NET 是否同時適用於桌面和 Web 應用程式？

答：是的，Aspose.Words for .NET 是一個多功能函式庫，適用於桌面和 Web 應用程式。無論您是建立 Windows 應用程式還是基於 Web 的系統，您都可以輕鬆整合該程式庫。
