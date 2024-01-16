---
title: 資源 Steam 字體來源範例
linktitle: 資源 Steam 字體來源範例
second_title: Aspose.Words 文件處理 API
description: 了解如何使用資源流字體來源將自訂字體載入到 Aspose.Words for .NET 中。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/resource-steam-font-source-example/
---

在本教學中，我們將引導您了解如何將資源流字體來源與 Aspose.Words for .NET 結合使用。此字體來源可讓您從資源流載入字體，當您想要將自訂字體合併到應用程式中時，這非常有用。

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

## 步驟2：上傳文件並設定資源流字體來源
接下來，我們將使用以下命令載入文檔`Document`類別並使用以下命令設定資源流字體來源`FontSettings.DefaultInstance.SetFontsSources()`班級。這將允許 Aspose.Words 在資源流中尋找字體。

```csharp
//載入文件並設定資源流字體來源
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## 步驟 3：儲存文檔
最後，我們將儲存文件。字體將從指定的資源流載入並嵌入到文件中。

```csharp
//儲存文件
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### 使用 Aspose.Words for .NET 的 Resource Steam 字體來源範例的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 結論
在本教學中，您學習如何將資源流字體來源與 Aspose.Words for .NET 結合使用。此功能可讓您從資源來源載入字體，當您想要將自訂字體嵌入到文件中時，這非常有用。嘗試不同的字體並探索 Aspose.Words 為字體管理提供的可能性。

### 常見問題解答

#### Q：如何將資源流中的字體載入到 Aspose.Words 中？

答：要從 Aspose.Words 中的資源流載入字體，您可以使用`FontSettings`類和`SetFontsSources`方法使用資源流指定字型來源。這允許直接從資源流而不是從實體文件載入字體。

#### Q：在 Aspose.Words 中使用資源流指定字體來源有什麼好處？

A：使用資源流指定字型來源有幾個優點：
- 允許您從應用程式內建的資源載入字體，從而輕鬆部署和分發文件。
- 提高字體管理的靈活性，因為您可以根據需要從不同的資源流載入字體。

#### Q：如何將字體加入到 .NET 應用程式的資源流中？

答：要將字體新增至 .NET 應用程式的資源流中，您必須將字體檔案嵌入到專案資源中。然後，您可以使用特定於您的開發平台的方法存取這些字體檔案（例如，`GetManifestResourceStream`使用`System.Reflection`命名空間）。

#### Q：是否可以將不同資源流中的多種字體載入到單一 Aspose.Words 文件中？

答：是的，完全可以將不同資源流中的多種字體載入到單一 Aspose.Words 文件中。您可以使用指定多個字型來源`SetFontsSources`的方法`FontSettings`類，為每種字體提供適當的資源流。

#### Q：我可以使用哪些類型的資源流將字體載入到 Aspose.Words 中？

答：您可以使用不同類型的資源流將字體載入到Aspose.Words 中，例如.NET 應用程式中內建的資源流、來自外部文件的資源流、來自資料庫的資源流等。請務必提供適當的資源流。資源流是基於您的設定和需求。