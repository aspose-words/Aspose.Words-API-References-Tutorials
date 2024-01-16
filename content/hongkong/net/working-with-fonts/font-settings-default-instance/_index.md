---
title: 字體設定預設實例
linktitle: 字體設定預設實例
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何使用 Aspose.Words for .NET 在 Word 文件中配置預設字體設定。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/font-settings-default-instance/
---

在本教學中，我們將引導您了解如何使用 .NET 的 Aspose.Words 庫在 Word 文件中配置預設字體設定。預設字體設定可讓您指定載入和渲染文件時使用的字體來源。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫

## 步驟1：定義文檔目錄
首先，您需要將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：配置預設字體設定
接下來，我們將建立一個實例`FontSettings`使用`FontSettings.DefaultInstance`，然後我們將指定載入和渲染文件時使用的字體來源。在此範例中，我們使用系統字體來源和資料夾字體來源。

```csharp
//配置預設字體設定
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 步驟 3：上傳帶有字型設定的文檔
現在我們將使用載入文檔`LoadOptions`並指定要使用的字體設定。

```csharp
//使用字型設定載入文檔
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### 使用 Aspose.Words for .NET 的字體設定預設實例的範例原始碼 
```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 結論
在本教程中，我們了解如何使用 Aspose.Words for .NET 在 Word 文件中配置預設字體設定。透過指定載入和呈現文件時使用的字型來源，您可以控製文件中字型的外觀。請隨意使用此功能來自訂項目中的字體設定。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定預設字體？

答：要在 Aspose.Words 中設定預設字體，您可以使用`FontSettings`類和`DefaultFontName`屬性指定所需字體的名稱。

#### Q：我可以在 Aspose.Words 中指定預設字體大小嗎？

答：是的，您可以使用 Aspose.Words 指定預設字體大小`DefaultFontSize`的財產`FontSettings`班級。您可以設定所需的磅值。

#### Q：Aspose.Words 可以設定預設字體顏色嗎？

答：是的，您可以使用 Aspose.Words 設定預設字體顏色`DefaultColor`的財產`FontSettings`班級。您可以使用 RGB 值或預先定義名稱來指定顏色。

#### Q：預設字體設定是否適用於所有文件？

答：是的，預設字體設定適用於在 Aspose.Words 中建立或編輯的所有文檔，除非為單一文檔設定了特定設定。