---
title: 設定字體資料夾系統和自訂資料夾
linktitle: 設定字體資料夾系統和自訂資料夾
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時設定係統和自訂字體資料夾的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

在本教程中，我們將引導您完成使用 Aspose.Words for .NET 渲染文件時設定係統字體資料夾和自訂資料夾的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何指定多個字體資料夾，包括系統資料夾和自訂資料夾，以便在使用 Aspose.Words for .NET 渲染文件時使用。

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

## 步驟 3：設定係統和自訂字型資料夾
現在您可以使用以下命令設定係統字體資料夾和自訂資料夾`FontSettings`類和`SetFontsSources()`方法。首先，您需要使用以下命令檢索依賴環境的字體來源列表`GetFontsSources()`並將其儲存在列表中。然後你可以建立一個新的實例`FolderFontSource`指定包含字型的自訂資料夾的路徑。將此實例新增至現有字體來源清單。最後，使用`SetFontsSources()`使用新清單更新字體來源。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 第 4 步：應用程式字體設定
接下來，您需要使用以下命令將字體設定套用到您的文檔`FontSettings`的財產`Document`班級。

```csharp
doc.FontSettings = fontSettings;
```

## 步驟5：保存渲染的文檔
最後，您可以將渲染的文檔儲存到檔案中

  使用`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### 使用 Aspose.Words for .NET 設定字體資料夾系統和自訂資料夾的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//檢索預設搜尋的與環境相關的字體來源數組。
//例如，這將包含 Windows 電腦上的「Windows\Fonts\」來源。
//我們將此陣列新增至新清單中，以便更輕鬆地新增或刪除字體條目。
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//新增一個新的資料夾來源，它將指示 Aspose.Words 在以下資料夾中搜尋字體。
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//將包含我們的字體的自訂資料夾新增至現有字體來源清單。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時設定係統字體資料夾和自訂資料夾。透過遵循此逐步指南，您可以輕鬆指定在渲染文件時使用的多個字體資料夾，包括系統資料夾和自訂資料夾。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以控制和自訂根據您的特定需求渲染文件時使用的字體來源。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定係統字體資料夾？

答：要在 Aspose.Words 中設定係統字體資料夾，您無需執行任何操作。 Aspose.Words 會自動使用作業系統上安裝的系統字型。

#### Q：如何在 Aspose.Words 中設定自訂字體資料夾？

答：要在 Aspose.Words 中設定自訂字體資料夾，您可以使用`SetFontsFolders`的方法`Fonts`指定自訂字型資料夾位置的類別。

#### Q：我可以在 Aspose.Words 中指定多個自訂字體資料夾嗎？

答：是的，您可以使用 Aspose.Words 中指定多個自訂字體資料夾`SetFontsFolders`的方法`Fonts`帶有資料夾位置清單的類別。

#### Q：如何查看 Aspose.Words 中定義的字體資料夾？

要檢查 Aspose.Words 中定義的字體資料夾，您可以使用`GetFolders`的方法`Fonts`類別來取得配置的字體資料夾的清單。

#### Q：Aspose.Words 中自訂資料夾字體是否優先於系統字體？

答：是的，在 Aspose.Words 中自訂資料夾字體優先於系統字體。如果自訂資料夾和系統字體中都存在某種字體，Aspose.Words 將使用自訂資料夾中的版本。