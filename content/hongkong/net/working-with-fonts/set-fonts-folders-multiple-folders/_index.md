---
title: 設定字體資料夾多個資料夾
linktitle: 設定字體資料夾多個資料夾
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時設定多個字體資料夾的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 渲染文件時設定多個字體資料夾的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何在使用 Aspose.Words for .NET 渲染文件時指定要使用的多個字體資料夾。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯後的渲染文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入要渲染的文檔
然後您可以使用以下命令載入要渲染的文檔`Document`班級。請務必指定正確的文件路徑。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第三步：設定字體資料夾
現在您可以使用以下命令設定多個字體資料夾`FontSettings`類和`SetFontsFolders()`方法。您可以指定要在陣列中使用的字型資料夾的路徑。在此範例中，我們指定了兩個字型資料夾：「C:\MyFonts\」和「D:\Misc\Fonts\」。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 第 4 步：應用程式字體設定
接下來，您需要使用以下命令將字體設定套用到您的文檔`FontSettings`的財產`Document`班級。

```csharp
doc.FontSettings = fontSettings;
```

## 步驟5：保存渲染的文檔
最後，您可以使用以下命令將渲染的文檔儲存到檔案中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### 使用 Aspose.Words for .NET 設定字體資料夾多個資料夾的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//請注意，此設定將覆蓋預設搜尋的任何預設字體來源。現在只會搜尋這些資料夾
//渲染或嵌入字體時的字體。若要在保留系統字體來源的同時新增額外的字體來源，請同時使用 FontSettings.GetFontSources 和
//相反，FontSettings.SetFontSources。
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時設定多個字體資料夾。透過遵循此逐步指南，您可以輕鬆指定渲染文件時要使用的多個字體資料夾。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以控制和自訂根據您的特定需求渲染文件時使用的字體來源。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定多個字體資料夾？

答：要在Aspose.Words中設定多個字體資料夾，您可以使用`SetFontsFolders`的方法`Fonts`提供自訂字體資料夾位置清單的類別。

#### Q：設定多個字體資料夾是否會影響使用 Aspose.Words 處理的所有文件？

答：是的，設定多個字體資料夾會影響使用 Aspose.Words 處理的所有文件。定義字體資料夾後，Aspose.Words 將使用這些位置在所有文件中搜尋字體。

#### Q：我可以在 Aspose.Words 中定義多少個字體資料夾？

答：您可以在 Aspose.Words 中根據需要定義任意數量的字體資料夾。您可以定義的字體資料夾的數量沒有具體限制。

#### Q：如何查看 Aspose.Words 中定義的字體資料夾？

答：要檢查 Aspose.Words 中定義的字體資料夾，您可以使用`GetFolders`的方法`Fonts`類別來取得配置的字體資料夾的位置。

#### Q：字體資料夾是否需要包含特定字體？

答：是的，字體資料夾應包含您要在 Word 文件中使用的字體。 Aspose.Words在處理文件時將在指定資料夾中尋找字體。