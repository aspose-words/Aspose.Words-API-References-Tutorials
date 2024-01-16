---
title: 渲染時指定預設字體
linktitle: 渲染時指定預設字體
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時指定預設字體的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/specify-default-font-when-rendering/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 渲染文件時指定預設字體的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何指定使用 Aspose.Words for .NET 渲染文件時所使用的預設字體。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯後的渲染文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入要渲染的文檔
接下來，您需要使用以下命令載入要渲染的文檔`Document`班級。請務必指定正確的文件路徑。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第三步：設定預設字體
現在，您可以透過建立一個實例來指定渲染時使用的預設字體`FontSettings`類別並設定`DefaultFontName`的財產`DefaultFontSubstitution`反對`DefaultFontSubstitution`目的`SubstitutionSettings`的`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 步驟 4：儲存渲染的文檔
最後，您可以使用以下命令將渲染的文檔儲存到檔案中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### 使用 Aspose.Words for .NET 渲染時指定預設字體的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//如果在渲染期間找不到此處定義的預設字體，則
//而是使用機器上最接近的字體。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時指定預設字體。透過遵循此逐步指南，您可以輕鬆設定渲染文件時使用的預設字體。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以根據您的特定需求控制和自訂文件的呈現。

### 常見問題解答

#### Q：在 Aspose.Words 中轉換為 PDF 時如何指定預設字體？

答：要在 Aspose.Words 中轉換為 PDF 時指定預設字體，您可以使用`PdfOptions`類別並設定`DefaultFontName`屬性到所需字體的名稱。

#### Q：轉換為 PDF 時預設字體不可用怎麼辦？

答：如果轉換為 PDF 時指定的預設字體不可用，Aspose.Words 將使用替換字體來顯示轉換後文件中的文字。這可能會導致外觀與原始字體略有不同。

#### Q：我可以為其他輸出格式（例如 DOCX 或 HTML）指定預設字體嗎？

答：是的，您可以透過使用適當的轉換選項並為每個格式設定相應的屬性，為其他輸出格式（例如 DOCX 或 HTML）指定預設字體。

#### Q：如何查看Aspose.Words 中指定的預設字體？

答：要檢查 Aspose.Words 中指定的預設字體，您可以使用`DefaultFontName`的財產`PdfOptions`類別並檢索配置的字體的名稱。

#### Q：是否可以為文件的每個部分指定不同的預設字型？

答：是的，可以使用特定於每個部分的格式選項為文件的每個部分指定不同的預設字型。然而，這需要使用 Aspose.Words 功能對文件進行更高級的操作。