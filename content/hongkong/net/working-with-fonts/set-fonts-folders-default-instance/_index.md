---
title: 設定字體資料夾預設實例
linktitle: 設定字體資料夾預設實例
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時設定預設字體資料夾的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-fonts-folders-default-instance/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 渲染文件時設定預設字體資料夾的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何設定使用 Aspose.Words for .NET 渲染文件時要使用的預設字體資料夾。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯後的渲染文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：設定預設字型資料夾
然後您可以使用以下命令設定預設字體資料夾`FontSettings.DefaultInstance`類和`SetFontsFolder()`方法。指定要用作預設資料夾的字型資料夾的路徑。

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## 第 3 步：載入要渲染的文檔
現在您可以使用以下命令載入要渲染的文檔`Document`班級。請務必指定正確的文件路徑。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 4：儲存渲染的文檔
最後，您可以使用以下命令將渲染的文檔儲存到檔案中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### 使用 Aspose.Words for .NET 設定字體資料夾預設實例的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時設定預設字體資料夾。透過遵循此逐步指南，您可以輕鬆指定在渲染文件時將哪個字體資料夾用作預設資料夾。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以控制和自訂根據您的特定需求渲染文件時使用的字體來源。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定預設字體資料夾？

答：要在 Aspose.Words 中設定預設字體資料夾，您必須使用`Fonts`類和`SetFontsFolders`指定自訂字型資料夾位置的方法。

#### Q：設定預設字體資料夾是否會影響使用 Aspose.Words 處理的所有 Word 文件？

答：是的，設定預設字體資料夾會影響所有使用 Aspose.Words 處理的 Word 文件。設定預設字體資料夾後，Aspose.Words 將使用這些位置在所有文件中搜尋字體。

#### Q：我可以在 Aspose.Words 中設定多個預設字體資料夾嗎？

答：是的，您可以在 Aspose.Words 中設定多個預設字體資料夾。您只需使用指定自訂字型資料夾的位置`SetFontsFolders`的方法`Fonts`班級。

#### Q：如何檢查 Aspose.Words 中目前設定的預設字體資料夾？

答：要檢查 Aspose.Words 中目前定義的預設字體資料夾，您可以使用`GetFolders`的方法`Fonts`類別來取得配置的字體資料夾的位置。

#### Q：設定預設字體資料夾是否允許我在 Word 文件中使用自訂字體？

答：是的，透過設定預設字體資料夾，您可以在 Word 文件中使用自訂字體。您只需將字體放置在指定的資料夾中，Aspose.Words 將在產生或操作文件時使用它們。