---
title: 取得可用字體列表
linktitle: 取得可用字體列表
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何取得 Aspose.Words for .NET 中可用的字體清單。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/get-list-of-available-fonts/
---
在本教程中，我們將解釋如何取得 Aspose.Words for .NET 中可用的字體清單。可用字體清單可讓您了解可以在文件中使用哪些字體。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

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

## 第 2 步：配置字體來源
接下來，我們將建立一個實例`FontSettings`並使用以下命令取得現有字體來源`GetFontsSources()`方法。我們還將透過指定包含字體的資料夾來新增新的字體來源。

```csharp
//配置字體來源
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

//新增的字體來源
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 步驟 3：取得可用字體列表
現在我們將使用以下命令瀏覽可用字體`GetAvailableFonts()`第一個更新的字體來源上的方法。

```csharp
//取得可用字體列表
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### 使用 Aspose.Words for .NET 取得可用字體清單的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//新增一個新的資料夾來源，它將指示 Aspose.Words 在以下資料夾中搜尋字體。
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//將包含我們的字體的自訂資料夾新增至現有字體來源清單。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## 結論
在本教程中，我們了解如何取得 Aspose.Words for .NET 中可用的字體清單。這可以讓您知道可以在文件中使用哪些字體。請隨意使用此功能來選擇適合您需求的字體。

### 常見問題解答

#### Q：如何檢索 Aspose.Words 中可用的字體清單？

答：要檢索 Aspose.Words 中可用的字體列表，您可以使用`FontsProvider`類和`GetAvailableFonts`方法。此方法將傳回系統上安裝的所有字型的清單。

#### Q：我可以在 Aspose.Words 中按特定條件過濾可用字體清單嗎？

答：是的，您可以使用特定條件過濾 Aspose.Words 中可用的字體清單。例如，您可以按系列、樣式或語言過濾字體。

#### Q：如何在 Word 文件中使用可用字型清單？

答：要使用 Word 文件中可用的字體列表，您可以瀏覽該列表並使用 Word 文件的方法和屬性選擇適當的字體。`FontSettings` Aspose.Words 中的類別。