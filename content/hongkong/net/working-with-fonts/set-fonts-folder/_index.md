---
title: 設定字體資料夾
linktitle: 設定字體資料夾
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中設定字體目錄並確保文件中使用的字體的可用性。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-fonts-folder/
---
在本教程中，我們將向您展示如何在 Aspose.Words for .NET 中設定字體目錄。您將學習如何指定包含 Word 文件中使用的字型的目錄。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫

## 步驟1：定義文檔目錄
首先將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：設定字體目錄
建立一個實例`FontSettings`類別並使用`SetFontsFolder`方法指定包含字型的目錄。代替`"Fonts"`與實際字體目錄的名稱。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 步驟 3：載入帶有字型設定的文檔
使用`LoadOptions`類別來指定字體設定`FontSettings`選項。然後使用`Document`類別來使用這些選項載入文件。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### 使用 Aspose.Words for .NET 設定字體資料夾的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 結論
恭喜！現在您知道如何在 Aspose.Words for .NET 中設定字體目錄。您可以使用此功能來確保文件中使用的字體的可用性並確保字體顯示的一致性。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定自訂字體資料夾？

答：要在 Aspose.Words 中設定自訂字體資料夾，您可以使用`FontsFolder`類和`SetFontsFolders`方法指定包含字型的資料夾的路徑。

#### Q：我可以在 Aspose.Words 中設定多個字體資料夾嗎？

答：是的，您可以在 Aspose.Words 中設定多個字體資料夾，方法是調用`SetFontsFolders`使用您要使用的不同字型資料夾的路徑多次使用該方法。

#### Q：如果文件中使用的字體不存在於定義的字體資料夾中，會發生什麼情況？

答：如果文件中使用的字體不存在於 Aspose.Words 中定義的字體資料夾中，則會使用替代字體。這可以確保文件中的文字始終正確顯示，即使原始字體不可用。

#### Q：Aspose.Words 中定義的字體資料夾是否優先於系統上安裝的字體？

答：是的，Aspose.Words 中定義的字體資料夾優先於系統上安裝的字體。這意味著，如果定義的字體資料夾和系統字體中都存在同名字體，則在處理 Word 文件時將使用字體資料夾中的版本。